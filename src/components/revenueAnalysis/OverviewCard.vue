<template>
    <div>
        <div class="w-full flex justify-between gap-6">
            <div class="w-1/3 bg-gray-200 rounded-xl cursor-pointer p-5 shadow-md hover:bg-gray-300 text-[#333]">
                <div class="flex justify-between text-4xl font-semibold">
                    <h1 class="">Orders</h1>
                    <i class='bx bx-cart-add'></i>
                </div>
                <h1 class="text-3xl mt-4">{{ totalOrders }}</h1>
            </div>
            <div class="w-1/3 bg-gray-200 rounded-xl cursor-pointer p-5 shadow-md hover:bg-gray-300 text-[#333]">
                <div class="flex justify-between text-4xl font-semibold">
                    <h1 class="">Sales</h1>
                    <i class='bx bx-purchase-tag'></i>
                </div>
                <h1 class="text-3xl mt-4">${{ totalSales }}K</h1>
            </div>
            <div class="w-1/3 bg-gray-200 rounded-xl cursor-pointer p-5 shadow-md hover:bg-gray-300 text-[#333]">
                <div class="flex justify-between text-4xl font-semibold">
                    <h1 class="">Products</h1>
                    <i class='bx bx-category-alt'></i>
                </div>
                <h1 class="text-3xl mt-4">{{ productLength }}</h1>
            </div>
        </div>
    </div>
</template>

<script setup>
import { storeToRefs } from 'pinia';
import { useSalesStore } from '../../stores/sales.js';
import { useProductStore } from '../../stores/product';

const productStore = useProductStore();
const { totalSales, totalOrders } = useSalesStore();
const { productLength } = storeToRefs(productStore);

productStore.getProductAction();
</script>