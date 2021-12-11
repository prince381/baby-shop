<template>
    <div class="item">
        <div class="item-img">
            <img :src="require(`../assets/images/${item.image}`)" alt="product image">
        </div>
        <div class="item-details">
            <p class="shop-name">{{ item.shop }}</p>
            <div class="detail-flex">
                <h3 class="name">{{ item.itemName }}</h3>
                <h3 class="price">{{ item.price }}</h3>
            </div>
            <p class="rating">
                <span class="stars">
                <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star-half-alt"></i>
                </span>
                <span>({{ item.rating }})</span>
            </p>
            <router-link to="/shops">
                <button class="btn btn-small">Shops Now</button>
            </router-link>
        </div>
    </div>
</template>

<script>
export default {
    props: ['item']
}
</script>

<style>
.item {
    width: 100%;
    max-width: 430px;
    max-height: 500px;
    background: #ededed;
    border-radius: 8px;
    overflow: hidden;
    margin-bottom: 2rem;
}

.item-img {
    width: 100%;
    height: calc(0.4 * 100vh);
    max-height: 50%;
}

.item-img img {
    width: 100%;
    height: 100%;
}

.item-details {
    padding: 1.3rem 1.3rem 2.5rem;
}

.shop-name {
    font-size: 1.3rem;
    line-height: 24px;
    margin-bottom: .7rem;
    color: #767581;
}

.detail-flex {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
}

.name {
    font-size: 1.4rem;
    color: #191d22;
    font-weight: 700;
}

.price {
    color: var(--main-color);
    font-size: 1.6rem;
}

.rating {
    margin-bottom: 2rem;
    font-size: 1.2rem;
}

.stars {
    margin-right: 5px;
    color: rgb(228, 195, 63);
}

.btn-small {
    padding: .7rem 1.2rem;
}

@media screen and (min-width: 768px) {
    .item {
        max-width: initial;
    }
}

@media screen and (min-width: 950px) {
    .shop-name {
        font-size: 1.5rem;
    }

    .name {
        font-size: 1.9rem;
    }

    .price {
        font-size: 2.2rem;
    }
}

@media screen and (min-width: 1300px) {
    .item {
        max-width: 430px;
    }

    .item-details {
        padding: 1.5rem 1.5rem 3.5rem;
    }

    .rating {
        margin-bottom: 3.2rem;
    }
}
</style>