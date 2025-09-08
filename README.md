# 20 Filters Project

A JavaScript project that allows users to filter items dynamically based on categories or search input.  
This project is great for practicing DOM manipulation, event listeners, and working with arrays of objects.

---

## Features
- Filter items by category with buttons  
- Search/filter items dynamically using input text  
- Responsive and clean layout  

---

## Built With
- **HTML5** for structure  
- **CSS3** for styling  
- **JavaScript (ES6)** for interactivity  

---

## Demo Preview
[20 Filters Project](https://devliwa.github.io/20-filters/)
<img width="1255" height="636" alt="Screenshot 2025-09-08 at 5 02 57 AM" src="https://github.com/user-attachments/assets/599003cf-0cd4-4b9a-8046-61c6edbc180f" />


---

## What I Learned
- Dynamically showing/hiding content based on user input  
- Handling multiple filter options simultaneously  
- Updating the DOM efficiently for a smooth user experience

  
#### HTML Structure

- section.products

  - div.filters-container
  - div.products-container

- .filters-container

  - form.input-form
    - input.search-input
  - h5(company)
  - article.companies
    - button.company-btn(temp values)

- .products-container
  - article.product
    - img.product-img.img (src from products.js)
    - footer
      - h5.product-name(name)
      - span.product-price(price)

#### Display Products

- import products
- make a copy and assign to new variable (use let keyword)
- select .products-container
- setup a function displayProducts, iterate over products, display them

#### Filter Based On Text

- select form, input
- listen for 'keyup' events on form
- get input value
- filter based on the input value
- call displayProducts

```js
// Text Filter

const form = document.querySelector('.input-form');
const searchInput = document.querySelector('.search-input');

form.addEventListener('keyup', () => {
  // keyup - fired when key released
  const inputValue = searchInput.value;
  filteredProducts = products.filter((product) => {
    return product.title.toLowerCase().includes(inputValue);
  });
  displayProducts();
});
```

#### Empty Array

- displayProducts()
- check length of filteredProducts
- if list.length < 1
- set productsContainer = some text

#### Display Filter Buttons

- select .companies
- create function displayButtons
- get only unique companies (set)
- iterate over results
- return button with data-id
- set .companies innerHTML equal to result

#### Filter Based on Company

- add event listener on .companies
- look for event.target
- if contains .company-btn proceed
  - if 'all' return all products (copy)
  - else filter based on company value
- set search value ''
- call displayProducts
