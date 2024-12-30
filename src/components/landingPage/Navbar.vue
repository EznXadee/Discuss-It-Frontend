<template>
    <v-app-bar :elevation="2">
<!-- <template v-slot:prepend>
    <v-app-bar-nav-icon></v-app-bar-nav-icon>
</template> -->

<v-app-bar-title>
    <div class="maincontent">
        <v-img src="@/assets/logo.svg" alt="logo" max-height="40" class="back"/>
    <v-select
    class="select"
    style="background-color:transparent;"
    label="Topics"
    :items="['California', 'Colorado', 'Florida', 'Georgia', 'Texas', 'Wyoming']"
></v-select>
    

<v-autocomplete
            append-inner-icon="mdi-magnify"
            class="search"
            density="comfortable"
            menu-icon=""
            placeholder="Search"
            
            style="max-width: 350px;
            margin-top: 20px;
            margin-left:0px
            "
            theme="light"
            variant="solo"
            auto-select-first
            item-props
            rounded
          ></v-autocomplete>
</div>
</v-app-bar-title>


<template v-slot:append>
    <div class="buttons">
        
        <v-btn class="member" >Member Login</v-btn>
        
        <v-btn class="expert"> Expert Login</v-btn>
    </div>
</template>
</v-app-bar>
</template>
<script>

export default {
name: 'Navbar',
}
</script>
<style scoped >
    .back{
        max-width: 200px;
        min-width: 116px;
    }
    .select{
        max-width: 150px;
        margin-top: 10px;
        max-height: 150px;
    }
    .maincontent{
        display: flex;
        justify-content: flex-start;
        align-items: center;
        gap: 20px;
        
    }
    .buttons{
        display: flex;
        justify-content: flex-end;
        align-items: center;
        gap: 20px;
        margin-right: 50px;
    }
    .member{
        background-color: #1766c0;
        color: #ffffff;
    }
    .expert{
        background-color: #292928;
        color: #ffffff;
    }
    @media screen and (max-width: 1000px){
        .maincontent{
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 20px;
            margin-right: 10px;
        }

        .expert{
            display: none;
        }
        .buttons{
            margin-right: 10px;
        }

        
    }
    @media screen and (max-width: 666px){
        .search{
            display: none;
        }

        .back{
            max-width: 116px;
        }
    }

    @media screen and (max-width: 450px){
        .member{
            max-width: 100px;
            font-size: 10px;
        }
        .buttons{
            gap: 10px;
            margin: 0;
        }
    }
</style>