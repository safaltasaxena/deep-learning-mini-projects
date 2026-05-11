# ⚡ TensorFlow Data Pipeline Optimization – Prefetch & Cache

📌 A hands-on mini project demonstrating how to measure and optimize performance of TensorFlow input pipelines using:

- 🚀 prefetch()
- 💾 cache()

---

## 📖 About

Efficient data pipelines are critical for high-performance deep learning.

This project focuses on:
- Simulating real-world I/O latency
- Measuring pipeline performance
- Optimizing pipelines using:
  - Prefetching
  - Caching

---

## 🧪 Simulating a Slow Dataset

```python
import tensorflow as tf
import time

class FileDataSet:
   @staticmethod
   def read_files_in_bacthes(num_samples):
    time.sleep(0.03)
    for sample_idx in range(num_samples):
      time.sleep(0.015)
      yield (sample_idx,)

   def __new__(cls, num_samples=3):
      return tf.data.Dataset.from_generator(
          cls.read_files_in_bacthes,
          output_signature=tf.TensorSpec(shape=(1,), dtype=tf.int64),
          args=(num_samples,)
      )
```

---

## ⏱️ Benchmark Function

```python
def benchmark(dataset, num_epochs=2):
  for epoch_num in range(num_epochs):
    for sample in dataset:
      time.sleep(0.01)
```

---

## 🚫 Without Optimization

```python
%%timeit
benchmark(FileDataSet())
```

Data loading and training happen sequentially → slower execution.

---

## 🚀 Prefetch Optimization

### Prefetch (buffer = 1)

```python
%%timeit
benchmark(FileDataSet().prefetch(1))
```

### Prefetch (AUTOTUNE)

```python
%%timeit
benchmark(FileDataSet().prefetch(tf.data.AUTOTUNE))
```

Prefetch overlaps data loading and model execution.

---

## 💾 Cache Optimization

### Basic Dataset

```python
dataset = tf.data.Dataset.range(5)
```

### Apply Transformation

```python
dataset = dataset.map(lambda x: x**2)
```

### Cache Results

```python
dataset = dataset.cache()

list(dataset.as_numpy_iterator())
list(dataset.as_numpy_iterator())
```

Second run is faster (no recomputation).

---

## 🧠 Expensive Mapping Function

```python
def mapped_fnc(S):

  def _py_fnc(val_tensor):
    import time
    time.sleep(0.03)
    return val_tensor.numpy()

  output_list = tf.py_function(
      func=_py_fnc,
      inp=[S[0]],
      Tout=[tf.int64]
  )

  output_tensor = output_list[0]
  output_tensor.set_shape([])

  return (output_tensor,)
```

---

## ⏱️ Benchmark Without Cache

```python
%%timeit -n1 -r7
benchmark(FileDataSet().map(mapped_fnc), 5)
```

---

## 🚀 Benchmark With Cache

```python
%%timeit -n1 -r7
benchmark(FileDataSet().map(mapped_fnc).cache(), 5)
```

---

## 📊 Observations

| Optimization | Effect |
|-------------|--------|
| ❌ No Prefetch | CPU/GPU waits for data |
| ✅ Prefetch | Overlaps compute + loading |
| ❌ No Cache | Recomputes every epoch |
| ✅ Cache | Reuses computed data |

---

## 🧠 Key Concepts

- tf.data.Dataset
- prefetch()
- cache()
- tf.data.AUTOTUNE
- Performance benchmarking

---

## ⚠️ Common Pitfalls

- Small prefetch buffer → low improvement  
- Large cache → memory issues  
- Wrong cache placement  
- Overuse of py_function  

---

## 🚀 Future Improvements

```python
dataset = dataset.map(..., num_parallel_calls=tf.data.AUTOTUNE) \
                 .cache() \
                 .prefetch(tf.data.AUTOTUNE)
```

- Use real datasets
- Integrate with model training

---

## ▶️ Usage

```bash
pip install tensorflow
```

Run the notebook to test performance improvements.

---

## 📌 Conclusion

Using prefetch() and cache() can significantly improve training speed by:

- Reducing idle time
- Avoiding recomputation
- Improving pipeline efficiency

---

🚀 Part of my Deep Learning journey — focusing on TensorFlow performance optimization.
