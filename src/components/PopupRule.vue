<template>
  <div class="popup" :class="getClassPopup">
    <div class="rule">
      <!-- <h1>Luật chơi</h1> -->
      <h3>
        Cậu nghĩ đây là 1 trò chơi ư. Dù cậu có quay xúc xắc được bao nhiêu điểm thì cũng đâu có quan trọng. Hôm nay là
        ngày của cậu .Chúc cậu luôn tự tin, mạnh mẽ và đầy sức sống. Hãy dám nghĩ lớn, hướng tới mục tiêu và không ngừng
        phấn đấu. Chúc cậu luôn được trải nghiệm những niềm vui, may mắn và thành công trong cuộc sống.Cảm ơn vì đã xuất
        hiện trong cuộc sống của tớ.❤️❤️❤️
      </h3>
      <audio id="player" autoplay loop>
        <source src="" type="audio/mp3" />
      </audio>
      <button v-on:click="confirm" class="confirm">hiuhiu</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'popup-rule',
  props: {
    isOpenPopup: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    confirm() {
      this.$emit('handleConfirm');
    },
  },
  computed: {
    getClassPopup() {
      return {
        'open-popup': this.isOpenPopup,
      };
    },
  },
};
</script>

<style>
.popup {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0);
  opacity: 0;
  visibility: hidden;
  transition: all 0.3s ease;
}
.open-popup {
  opacity: 1;
  visibility: visible;
}
.rule {
  width: 350px;
  height: 300px;
  background-color: #fff;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) scale(1.2);
  position: absolute;
  transition: all 0.3s ease;
}
.open-popup .rule {
  transform: translate(-50%, -50%) scale(1);
}
.rule h3 {
  text-align: center;
  margin-top: 10px;
  margin-bottom: 10px; /* Khoảng cách dưới 10px */
  font-family: 'Your Font Name', sans-serif; /* Thay 'Your Font Name' bằng tên font chữ bạn muốn sử dụng */
  font-size: 16px; /* Kích thước font chữ */
}
.rule .confirm {
  cursor: pointer;
  background-color: white;
  margin: 10px;
  transition: all 0.3s ease;
  padding: 10px;
  /* align-items: center;
  text-align: center; */
  border: 1px solid white;
  /* margin: 0px auto; */
}
.rule .confirm:hover {
  /* color: white; */
  background-color: white;
}
@media screen and (max-width: 768px) {
  .popup {
    max-width: 80%; /* Thay đổi kích thước popup khi màn hình nhỏ hơn 768px */
    max-height: 80%; /* Thay đổi kích thước popup khi màn hình nhỏ hơn 768px */
  }
}

.rule h3 {
  text-align: center;
  font-family: 'Your Font Name', sans-serif;
  font-size: 16px;
}

.rule .confirm {
  display: block;
  margin: 0 auto; /* Căn giữa nút confirm */
  padding: 10px 20px;
  cursor: pointer;
  background-color: #ffffff;
  border: 1px solid #000000;
  border-radius: 5px;
  transition: all 0.3s ease;
}

.rule .confirm:hover {
  background-color: #000000;
  color: #ffffff;
}
</style>
