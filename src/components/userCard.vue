<template>
    <div id="user-card">
        <h1>Lorem ipsum dolor sit amet.</h1>
        <div class="main-information">
            <img src="../assets/kouch.jpg" width="500px" alt="">
            <div class="info">
                <h2>
                    {{ getAuthorFullName }} 
                </h2>
                <strong>Biznes-Kouch</strong>
               <ul>
                   <li>Lorem ipsum dolor sit amet.</li>
                   <li>Lorem ipsum dolor sit amet.</li>
               </ul>
                <p>Users: {{ users.length }}</p>
                <ul>
                    <li v-for="(user, index) in users" :key="index">
                        {{ index +  getUserFullName(user) }} <br> <br>
                    </li>
                </ul>
                <br><br>
                Sahifalar 
                <button type="button" @click="currentPage--">
                    Orqaga
                </button>
                <button 
                v-for="page in pages" 
                :key="page"
                type="button"
                @click="currentPage = page"
                >
                 
                    {{ page }}
                </button>
                <button type="button" @click="currentPage++">
                    Oldinga
                </button>
                <br><br>
                 {{ pages }} dan {{ currentPage }}
            </div>
        </div>
        
    </div>
</template>

<script>
export default {
    name: 'userCard',
    data() {
        return {
            firstName: 'Ivan',
            lastName: 'Ivanovich',
            secondName: 'Ivanov',
            users: [
                {
                    firstName: 'Abdulvoris',
                    secondName: 'Tulkinovich',
                    lastName: 'Erkinov'
                },
                {
                    firstName: 'Iskandar',
                    secondName: 'Tulkinovich',
                    lastName: 'Erkinov'
                },
                {
                   firstName: 'Abdulloh',
                    secondName: 'Tulkinovich',
                    lastName: 'Erkinov'
                }
            ],
            pages: 3,
            currentPage: 1,
        }
    },
    
    computed: {
        getAuthorFullName() {
            return `${this.firstName} ${this.lastName} ${this.secondName}`
        }
    },
    methods: {
        getUserFullName(user) {
            return `${user.firstName} ${user.lastName} ${user.secondName}`
        },
        loadUsers(page) {
            console.log(page);
        },
        
    },
    watch: {
        currentPage(page) {
            this.loadUsers(page)
        }   
    }
}
</script>

<style scoped>
  .user-card {
    margin-top: 40px;
  }
  .info {
    margin-left: 50px;
  }
  h2 {
    margin-bottom: 14px;
  }
  .main-information img, .info{
      width: 50%;
      
  }
  .main-information {
      width: 800px;
      display: flex;
      align-items: center;
  }
</style>
