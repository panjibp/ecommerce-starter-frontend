<template>
    <div>
        <!-- Header Section Begin -->
        <header class="header-section">
            <div class="header-top">
                <div class="container">
                    <div class="ht-left">
                        <div class="mail-service">
                            <i class=" fa fa-envelope"></i> panji.bp.bp@gmail.com
                        </div>
                        <div class="phone-service">
                            <i class=" fa fa-phone"></i> +62 812-1245-8369
                        </div>
                    </div>
                </div>
            </div>
            <div class="container">
                <div class="inner-header">
                    <div class="row">
                        <div class="col-lg-2 col-md-2">
                            <div class="logo">
                                <router-link to="/">
                                    <img src="img/logo_website_shayna.png" alt="" />
                                </router-link>
                            </div>
                        </div>
                        <div class="col-lg-7 col-md-7"></div>
                        <div class="col-lg-3 text-right col-md-3">
                            <ul class="nav-right">
                                <li class="cart-icon" style="font-size: 18px;">
                                    Keranjang Belanja &nbsp;
                                    <a href="#">
                                        <i class="icon_bag_alt"></i>
                                        <span>{{ keranjangUser.length }}</span>
                                    </a>
                                    <div class="cart-hover" v-if="keranjangUser.length > 0">
                                        <div class="select-items">
                                            <table>
                                                <tbody>
                                                    <tr v-for="keranjang in keranjangUser" :key="keranjang.id">
                                                        <td class="si-pic">
                                                            <img :src="keranjang.photo" class="photo-item" alt="" />
                                                        </td>
                                                        <td class="si-text">
                                                            <div class="product-selected">
                                                                <p>Rp{{ keranjang.price }} x 1</p>
                                                                <h6>{{ keranjang.name }}</h6>
                                                            </div>
                                                        </td>
                                                        <td @click="removeItem(keranjang.id)" class="si-close">
                                                            <i class="ti-close"></i>
                                                        </td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                        <div class="select-total">
                                            <span>total:</span>
                                            <h5>Rp{{ totalHarga }}</h5>
                                        </div>
                                        <div class="select-button">
                                            <a href="#" class="primary-btn view-card"><router-link to="/cart" style="color:#FFF;">VIEW CARD</router-link></a>
                                            <a href="#" class="primary-btn checkout-btn">CHECK OUT</a>
                                        </div>
                                    </div>
                                    <div class="cart-hover" v-else>
                                        <div class="select-items">
                                            <table>
                                                <tbody>
                                                    <tr>
                                                        <td>Keranjang kosong</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                        <div class="select-total">
                                            <span>total:</span>
                                            <h5>Rp0</h5>
                                        </div>
                                        <div class="select-button">
                                            <a href="#" class="primary-btn view-card">VIEW CARD</a>
                                            <a href="#" class="primary-btn checkout-btn">CHECK OUT</a>
                                        </div>
                                    </div>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </header>
        <!-- Header End -->
    </div>
</template>

<script>
export default {
    name: 'HeaderShayna',
    data() {
        return {
            keranjangUser: []
        };
    },
    methods: {
        removeItem(idx) {
            // cari tahu id item yang akan dihapus
            let keranjangUserStorage = JSON.parse(localStorage.getItem('keranjangUser'));
            let itemKeranjangUserStorage = keranjangUserStorage.map(itemKeranjangUserStorage => itemKeranjangUserStorage.id);

            // cocokkan idx item dengan id yang ada di storage
            let index = itemKeranjangUserStorage.findIndex(id => id == idx);
            this.keranjangUser.splice(index, 1);

            const parsed = JSON.stringify(this.keranjangUser);
            localStorage.setItem('keranjangUser', parsed);
            window.location.reload();
        }
    },
    mounted() {
        if (localStorage.getItem('keranjangUser')) {
          try {
              this.keranjangUser = JSON.parse(localStorage.getItem('keranjangUser'));
          } catch(e) {
              localStorage.removeItem('keranjangUser');
          }
      }
    },
    computed: {
        totalHarga() {
            return this.keranjangUser.reduce(function(items, data) {
                return items + data.price;
            }, 0);
        }
    }
}
</script>

<style scoped>
.photo-item {
    width: 70px;
    height: 100px;
}
</style>