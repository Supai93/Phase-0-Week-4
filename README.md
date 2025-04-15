# Phase-0-Week-4
# Object Literals

## 1. Perkenalan

Dalam JavaScript, sebuah **object** adalah salah satu tipe data fundamental yang merupakan fondasi pemrograman JavaScript. **Object literal** adalah cara mudah untuk membuat object. Object didefinisikan dengan pasangan `key-value` dalam tanda kurung kurawal `{ }`. Setiap `property` terdiri dari sebuah "kunci" (disebut juga nama properti) dan sebuah value, dipisahkan titik dua `:`, dan tiap sepasang key-value dipisahkan tanda koma.

---

## 2. Syntax

```javascript
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 30,
  isEmployed: true
};
```

## 3. Mengakses Properti
### Tanda Dot
```javascript
console.log(person.firstName); // Output: John
```
### Tanda Kurung `[ ]`
```javascript
console.log(person["lastName"]); // Output: Doe
```
Tanda kurung berguna ketika kunci disimpan dalam suatu variabel, atau mengandung spasi/karakter spesial.


## 4. Menambah dan Mengubah Properti
```javascript
person.nationality = "American"; // Add new property
person.age = 31; // Modify existing property
```
Properti `nationality` adalah properti baru, mengapa? Definisi object `person` pada bagian syntax sebelumnya belum memiliki property `nationality`. Kita dapat langsung menambah dan memberi value pada properti yang belum pernah didefinisikan dan javascript secara otomatis akan menambahkannya. Fleksibel sekali, bukan?

## 5. Nested Objects
```javascript
const employee = {
  name: "Jane",
  position: "Developer",
  address: {
    street: "123 Main St",
    city: "New York",
    zip: "10001"
  }
};

console.log(employee.address.city); // Output: New York
```
Tidak ada batasan tipe data untuk properti. Bahkan properti dapat berupa object juga.

## 6. Metode Dalam Object
```javascript
const calculator = {
  value1: 0,
  value2: 0,

  add: function() {
    return this.value1 + this.value2;
  },
  subtract() {
    return this.value1 - this.value2;
  }
};

calculator.value1 = 5;
calculator.value2 = 3;

console.log(calculator.add());      // Output: 8
console.log(calculator.subtract()); // Output: 2
```
Metode adalah `function` yang didefinisikan didalam suatu object. Kata kunci `this` merujuk ke Object dimana metode itu dipanggil.

## Tugas-Tugas

### Tugas 1: Dasar Pembuatan Object
Buatlah object literal yang menggambarkan sebuah buku dengan properti untuk judul, penulis, tahun publikasi, dan ketersediaan buku. Lalu tampilkan output dari masing-masing properti.

<details>
<summary>Solution</summary>

```javascript
const book = {
  title: "JavaScript: The Good Parts",
  author: "Douglas Crockford",
  publicationYear: 2008,
  isAvailable: true
};

console.log(book.title);          // "JavaScript: The Good Parts"
console.log(book["author"]);      // "Douglas Crockford"
console.log(book.publicationYear); // 2008
console.log(book.isAvailable);     // true
```
</details>

### Tugas 2: Object Methods
Buatlah object persegi panjang dengan properti panjang dan lebar. Tambahkah metode untuk menghitung luas dan keliling. Tampilkan output kedua metode tersebut.
<details>
<summary>Solution</summary>

```javascript
const rectangle = {
  width: 10,
  height: 5,
  
  calculateArea() {
    return this.width * this.height;
  },
  
  calculatePerimeter() {
    return 2 * (this.width + this.height);
  }
};

console.log(`Area: ${rectangle.calculateArea()}`);           // Area: 50
console.log(`Perimeter: ${rectangle.calculatePerimeter()}`); // Perimeter: 30
```
</details>

### Tugas 3: Nested Objects
Buatlah object yang menggambarkan keranjang belanja dengan properti untuk item-item (array) dan informasi customer. Metode yang harus ada adalah: menambahkan item, menghitung total belanja, dan menampilkan rangkuman belanja.

<details>
<summary>Solution</summary>

```javascript
const shoppingCart = {
  customer: {
    name: "Jane Smith",
    email: "jane@example.com",
    address: {
      street: "456 Oak Ave",
      city: "Springfield",
      zipCode: "12345"
    }
  },
  items: [],
  
  addItem(product, quantity = 1) {
    this.items.push({
      product: product,
      quantity: quantity,
      subtotal: product.price * quantity
    });
  },
  
  calculateTotal() {
    let total = 0;
    for (const item of this.items) {
      total += item.subtotal;
    }
    return total;
  },
  
  displaySummary() {
    console.log(`Cart for ${this.customer.name}:`);
    
    for (const item of this.items) {
      console.log(`- ${item.quantity}x ${item.product.name}: $${item.subtotal.toFixed(2)}`);
    }
    
    console.log(`Total: $${this.calculateTotal().toFixed(2)}`);
  }
};

// Using the shopping cart
shoppingCart.addItem({ id: 1, name: "T-shirt", price: 19.99 }, 2);
shoppingCart.addItem({ id: 2, name: "Jeans", price: 49.99 }, 1);
shoppingCart.displaySummary();
```
</details>
