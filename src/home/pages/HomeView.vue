<!-- App.vue -->
<template>
  <div id="app">
    <main>
      <h1 class="corner-chef">Corner-Chef</h1>
      <div class="chat-container">
        <div class="chat-messages">
          <!-- 채팅 내용은 여기에 표시됨 -->
        </div>
        <div class="chat-input">
          <input type="text" placeholder="가지고 계신 재료를 입력해주시면 근사한 레시피를 알려드릴게요!" v-model="message" @keyup.enter="sendMessage">
          <button @click="sendMessage">🍳</button>
        </div>
      </div>
      <div class="info">
        <p>서울시 금천구 가산동 670 18층 | PaikJongWon@theborn.com | Tel. 0507-1353-7302</p>
      </div>
    </main>
  </div>  
</template>

<script>
import { mapActions, mapState } from "vuex";
import PopUpView from '@/popup/pages/HomePopup.vue'
const authenticationModule = "authenticationModule";

export default ({
  name: 'App',
  data() {
    return {
      message: '',
      messages: []
    }
  },
  // methods: {
  //   sendMessage() {
  //     if (this.message.trim()) {
  //       this.messages.push(this.message);
  //       this.message = '';
  //       // 여기에 챗봇 응답 로직을 추가할 수 있습니다
  //     }
  //   }
  // }
});
</script>

<style>
@font-face {
  font-family: 'Satisfy';
  font-style: normal;
  font-weight: 400;
  src: url(https://fonts.gstatic.com/s/satisfy/v11/rP2Hp2yn6lkG50LoCZOIHQ.woff2) format('woff2');
  font-display: swap;
}


.corner-chef {
  font-family: 'Satisfy', cursive;
}

#app::before {
  content: "";
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: url('@/assets/images/fixed/home_main_image.jpg');
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  opacity: 0.8;
  z-index: -1;
}

main {
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between; /* 이 부분을 유지합니다 */
  align-items: center;
  position: relative;
  z-index: 2;
  height: 100vh;
  padding: 50px 0; /* 상하 패딩을 동일하게 설정 */
  width: 100%;
  box-sizing: border-box; /* 패딩을 높이에 포함 */
}

h1 {
  font-size: 4rem;
  color: #fff;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
  margin-bottom: 2rem;
  text-align: center;
  width: 100%;
}

.chat-container {
  width: 80%;
  max-width: 600px;
  height: 60vh;
  background-color: rgba(255, 255, 255, 0.5);  /* 마지막 0.5는 투명도에 관한 설정*/
  border-radius: 10px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  margin: 0 auto;
}

.chat-messages {
  flex-grow: 1;
  overflow-y: auto;
  padding: 1rem;
}

.chat-input {
  display: flex;
  padding: 1rem;
  background-color: rgba(255, 255, 255, 1);  /* 마지막 1은 투명도에 관한 설정*/
}

.chat-input input {
  flex-grow: 1;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 20px;
  margin-right: 0.5rem;
}

.chat-input button {
  padding: 0.5rem;
  background-color: #FFD700;
  color: black;
  border: none;
  border-radius: 50%;
  cursor: pointer;
  width: 40px;
  height: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 25px;
}

.chat-input button:hover {
  background-color: #FFC000;
}

.info {
  width: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  color: #fff;
  text-align: center;
  padding: 10px;
  position: absolute;
  bottom: 0;
  /* left: 0; */
  right: 0;
}

.info p {
  margin: 0;
  font-size: 14px;
}
</style>

