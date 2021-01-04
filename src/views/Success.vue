<template>
    <div class="d-flex success-checkout align-items-center justify-content-center">
        <div class="col col-lg-4 text-center">
            <img src="img/success-buy.png" alt="" width="294" style="margin-right: 54px;">
            <h3 class="mt-4">
                Sukses Terbayar!
            </h3>
            <p class="mt-2">
                Silakan tunggu update terbaru via <b>email</b> yang sudah Anda daftarkan sebelumnya.
            </p>
            <router-link to="/" class="primary-btn pd-cart mt-3">Back to Home</router-link>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Success'
}
</script>