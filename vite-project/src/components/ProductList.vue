<template>
    <el-card>
        <h2>商品列表</h2>

        <el-table :data="products" >

        <el-table-column prop="name" label="商品名称" ></el-table-column>
        <el-table-column prop="price" label="价格" ></el-table-column>
        <el-table-column label="操作">
            <template #default="{row}">
                <el-button type="primary" @click="showProductDetails(row)">

                    查看详情

                </el-button>
            </template>
        </el-table-column>


        </el-table>
    </el-card>
</template>

<script setup lang="ts">

import { ref } from "vue"

import {ElCard ,ElTable,ElTableColumn,ElButton } from "element-plus";

import "element-plus/dist/index.css"

interface Product{
    name: string;
    price: number;
}

const products = ref<Product[]>([
   {name: "商品 A" , price: 100},
   {name: "商品 B" , price: 200},
   {name: "商品 C" , price: 300},
]);

const showProductDetails = (products: Product) => {
    alert(JSON.stringify(products));
};

</script>

<style scoped>

.el-card{
    max-width: 800px;
    margin: 20px auto;
}

</style>