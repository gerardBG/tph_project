<template>
    <div class="d-flex flex-row justify-content-around align-items-center w-100 borderPrimaryTop py-5 bg-secondaryGrey mobileFlex">
        <div class="d-flex flex-column">
            <p class="font-bold mb-1">Información legal</p>
            <ul class="noDots">
                <li>
                    <router-link to="/" class="colorPrimary underline-none"> Aviso legal </router-link>

                </li>
                <li>
                    <router-link to="/" class="colorPrimary underline-none"> Política de privacidad </router-link>
                </li>
            </ul>
        </div>
        <div>
            <p class="font-bold ">Información legal</p>
            <ul class="noDots">
                <li>
                    <router-link to="/" class="colorPrimary underline-none"> Aviso legal </router-link>

                </li>
                <li>
                    <router-link to="/" class="colorPrimary underline-none"> Política de privacidad </router-link>
                </li>
            </ul>
        </div>
        <div>
            <p class="font-bold ">Información legal</p>
            <ul class="noDots">
                <li>
                    <router-link to="/" class="colorPrimary underline-none"> Aviso legal </router-link>

                </li>
                <li>
                    <router-link to="/" class="colorPrimary underline-none"> Política de privacidad </router-link>
                </li>
            </ul>
        </div>
    </div>
</template>

<style scoped>
.noDots{
    list-style: none;
    padding: 0;
    margin: 0;
}
.colorPrimary{
    color: #359369;
}
.borderPrimaryTop{
    border-top: 2px solid #359369 ;
}

.underline-none{
    text-decoration: none;
}
.font-bold{
    font-weight: bold;
}
.bg-secondaryGrey {
  background-color: #f1f3f5bd;
}
@media (max-width: 900px){
    .mobileFlex{
        flex-direction: column !important;
        gap: 20px;
    }
}
</style>