<template>
    <div class="product-list">
        <div class="flex">
            <h2>Tables for you</h2>
            <input type="text" class="search ms-2" v-model="searchText">
            {{ searchText }}
            <button>Search</button>
        </div>

        <ul class="list-default flex">
            <li
            v-for="(product, index) in products"
            :key="index">
                <ProductCard 
                :title="product.title"
                :price="product.price"
                :imgUrl="product.imgUrl"
                :count="product.count"
                @addToBasket="addToBasket(index)"
                />
            </li>
        </ul>
    </div>
</template>

<script>
import ProductCard from '@/components/ProductCard'

export default {
    name: 'ProductList',
    components: { ProductCard },
    data() {
        return {
            searchText: '',
            products: [
                {
                    title: 'Стол Jim',
                    price: 19999,
                    imgUrl: 'https://hoff.ru/upload/iblock/8c9/8c989500ee8639b9e3aa267b1888b4af.jpg',
                    count: 30
                },
                {
                    title: 'Стол Monako',
                    price: 17199,
                    imgUrl: 'https://hoff.ru/upload/iblock/af2/af2d37161f217d4f489373be7da4a7a0.jpg',
                    count: 20
                },
                {
                    title: 'Стол с двумя ящиками Кварт MD 768',
                    price: 10999,
                    imgUrl: 'https://hoff.ru/upload/iblock/1cc/1ccb33b50e3e9cfa08629bf455e41855.jpg',
                    count: 23
                }
            ],
        }
    },
    methods: {
        addToBasket(index) {
            console.log(index);
        }
    }
}
</script>

<style scoped>
li {
  margin-right: 20px;
  list-style: none;
}
.top-information {
  align-items: center;
  
  margin-bottom: 22px;
}
h1 {
    margin-bottom: 0;
}
button {
    background-color: rgb(221, 56, 56);
    color: #fff;
    border: none;
    border-radius: 4px;
    padding: 8px 14px;
    display: block;
    cursor: pointer;
    margin-left: 10px;
}
.flex {
    display: flex;
    align-items: center;
}
.product-list h2 {
    margin-left: 50px;
}
.ms-2 {
    margin-left: 20px;
}
.search {
    padding: 3px 7px;
    border: 1px solid #f1f1f1;
    border-radius: 2px;
}
.search:focus {
    border-color: #c7c7c7 !important;
    outline: none;
}
</style>