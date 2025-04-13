# Phase-0-Week-4
# Object Literals

## 1. Perkenalan

Dalam JavaScript, sebuah **object literal** adalah cara mudah untuk membuat object. Object didefinisikan dengan pasangan `key-value` dalam tanda kurung `{ }`.
Setiap `property` terdiri dari sebuah "kunci" (disebut juga nama properti) dan sebuah value, dipisahkan titik dua (:), dan tiap sepasang key-value dipisahkan tanda koma.

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
  add: function(a, b) {
    return a + b;
  },
  subtract(a, b) {
    return a - b;
  }
};

console.log(calculator.add(5, 3));      // Output: 8
console.log(calculator.subtract(5, 3)); // Output: 2
```
Selayaknya anda membuat object dalam bahasa lain, object dalam javascript juga dapat mengandung metode (`function`) yang nantinya dapat dipanggil.
