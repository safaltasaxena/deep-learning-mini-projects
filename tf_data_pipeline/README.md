# 🧠 TensorFlow Data Pipeline – tf.data API (End-to-End)

📌 A hands-on mini project demonstrating how to build efficient **data pipelines**
using TensorFlow’s `tf.data` API for both **numerical data** and **image datasets**.

---

## 📖 About

Deep Learning models depend heavily on how efficiently data is loaded and processed.

This project demonstrates:

* Creating datasets from Python data
* Applying transformations (filter, map, shuffle, batch)
* Building an **end-to-end input pipeline**
* Loading and preprocessing **image datasets**

---

## 📊 Dataset

### 1️⃣ Numerical Dataset

```python
daily_sales_numbers = [21, 22, -108, 31, -1, 32, 34, 31]
```

* Contains both valid and invalid (negative) sales values

---

### 2️⃣ Image Dataset

Directory structure:

```
images/
  ├── cat/
  ├── dog/
```

* Total images: **130**
* Classes:

  * 🐱 Cat
  * 🐶 Dog

---

## 🧹 Data Pipeline (Numerical Data)

### 1️⃣ Create Dataset

```python
tf_dataset = tf.data.Dataset.from_tensor_slices(daily_sales_numbers)
```

---

### 2️⃣ Iteration

```python
for x in tf_dataset:
    print(x.numpy())
```

---

### 3️⃣ Filtering

Remove invalid values:

```python
tf_dataset = tf_dataset.filter(lambda x: x > 0)
```

---

### 4️⃣ Mapping

Convert USD → INR:

```python
tf_dataset = tf_dataset.map(lambda x: x * 72)
```

---

### 5️⃣ Shuffling

```python
tf_dataset = tf_dataset.shuffle(buffer_size=2)
```

---

### 6️⃣ Batching

```python
tf_dataset = tf_dataset.batch(2)
```

---

### ✅ Full Pipeline

```python
tf_dataset = tf.data.Dataset.from_tensor_slices(daily_sales_numbers)

tf_dataset = (
    tf_dataset
    .filter(lambda x: x > 0)
    .map(lambda x: x * 72)
    .shuffle(2)
    .batch(2)
)
```

---

## 🧠 Image Data Pipeline

### 1️⃣ Load Image Paths

```python
images_ds = tf.data.Dataset.list_files('images/*/*', shuffle=False)
```

---

### 2️⃣ Shuffle Dataset

```python
images_ds = images_ds.shuffle(200)
```

---

### 3️⃣ Train-Test Split

```python
train_size = int(image_count * 0.8)

train_ds = images_ds.take(train_size)
test_ds = images_ds.skip(train_size)
```

---

## 🖼️ Image Processing

### Extract Label

```python
def get_label(file_path):
    parts = tf.strings.split(file_path, os.path.sep)
    return parts[-2]
```

---

### Load & Resize Image

```python
def process_image(file_path):
    label = get_label(file_path)
    img = tf.io.read_file(file_path)
    img = tf.image.decode_jpeg(img)
    img = tf.image.resize(img, [128, 128])
    return img, label
```

---

### Apply Transformation

```python
train_ds = train_ds.map(process_image)
test_ds = test_ds.map(process_image)
```

---

## 🎯 Normalization

```python
def scale(image, label):
    return image / 255, label

train_ds = train_ds.map(scale)
```

---

## 🔍 Sample Output

```python
for image, label in train_ds.take(1):
    print(image.shape)  # (128, 128, 3)
    print(label)
```

---

## 🧠 Key Concepts Covered

* `tf.data.Dataset` basics
* Lazy evaluation
* Data transformations:

  * filter
  * map
  * shuffle
  * batch
* Image preprocessing pipeline
* Efficient input pipelines for deep learning

---

## ⚠️ Common Pitfalls

* Small shuffle buffer → poor randomness
* Forgetting normalization → unstable training
* Incorrect label extraction from file path
* Not batching → slower training

---

## 🚀 Future Improvements

* Add:

  * `prefetch()` for performance
  * `cache()` for faster reuse
* Convert labels to numeric (0/1)
* Build CNN model on top of dataset
* Use data augmentation

---

## ▶️ Usage

1. 📥 Install dependencies:

```bash
pip install tensorflow
```

2. 📂 Prepare dataset:

* Place images inside `images/cat` and `images/dog`

3. ▶️ Run notebook to:

* Build pipelines
* Process images
* Inspect batches

---

## 📌 Conclusion

This project demonstrates how to build **efficient and scalable data pipelines**
using TensorFlow.

Instead of manually loading data, `tf.data` enables:

* Faster training
* Cleaner code
* Better scalability

---

📎 Notebook reference: 

---

🚀 *Part of my Deep Learning journey focusing on efficient data handling with TensorFlow.*
