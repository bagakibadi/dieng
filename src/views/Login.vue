<template>
  <div class="contains">
    <div class="box">
      <div class="judul">
        <h1>Masuk</h1>
      </div>
      <form action="">
        <div class="forminput">
          <input type="email" placeholder="Email">
          <div class="msgerror">
            <p>Email Should use @</p>
          </div>
        </div>
        <div class="forminput">
          <input type="password" placeholder="Password">
          <div class="msgerror">
            <p>Email Should use @</p>
          </div>
        </div>
        <div class="remember">
          <div>
            <input type="checkbox" id="checkbox">
            <label for="checkbox">Remember Me</label>
          </div>
          <div>
            <router-link to="#">Lupa Password?</router-link>
          </div>
        </div>
        <div class="btn btn-primary">Masuk</div>
      </form>
      <div class="regist">
        <h1>Belum punya Akun?</h1>
        <router-link to="/signup">Daftar</router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {

};
</script>

<style lang="scss" scoped>
  .contains{
    width: 100%;
    height: 100vh;
    overflow: hidden;
    background: whitesmoke;
    display: flex;
    justify-content: center;
    align-items: center;
    .box{
      width: 500px;
      height: auto;
      border-radius: 8px;
      background: white;
      padding: 20px 40px;
      .judul{
        width: 100%;
        display: flex;
        justify-content: center;
        margin-bottom: 20px;
        h1{
          font-size: 32px;
        }
      }
      form{
        .forminput{
          width: 100%;
          input{
            width: 100%;
            padding: 10px 25px;
            border-radius: 5px;
            border: 1px solid #e7ebee;
            // margin: 10px 0;
            outline-color: #66afe9;
          }
          .msgerror{
            width: 100%;
            p{
              font-size: 14px;
              color: #666;
              padding-left: 10px;
              padding-top: 3px;
            }
          }
        }
        .remember{
          width: 100%;
          display: flex;
          align-items: center;
          justify-content: space-between;
          margin-bottom: 10px;
          label{
            margin-bottom: 0;
            margin-left: 5px;
            color: #444;
          }
          a{
            text-decoration: none;
          }
        }
        .btn{
          width: 100%;
          margin: 5px 0;
        }
      }
      .regist{
        width: 100%;
        display: flex;
        align-items: center;
        padding: 5px;
        h1{
          margin: 0;
          font-size: 16px;
          color: rgb(70, 70, 70);
        }
        a{
          margin: 0;
          text-decoration: none;
        }
      }
    }
  }
</style>
