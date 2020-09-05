<template>
  <div class="contains">
    <!-- Navbars -->
      <div class="navbars">
        <div class="logos">
          <img src="https://www.loket.com/images/logo-loket-white.png" alt="">
        </div>
        <div class="searchs"></div>
        <div class="infoacc"></div>
      </div>
    <!--  -->
    <!--  -->
      <div class="content">
        <div class="right">
          <div class="judul">
            <h1>Computing on the Edge with Kubernetes</h1>
            <p>Wed, Oct 21, 2020 at 7:00 PM to Thu, Oct 22, 2020 4:00 AM ()</p>
          </div>
          <div class="box">
            <div class="head">
              <h1>Ticket Buyer</h1>
            </div>
            <!-- Code === 2 -->
              <div v-if="code === 2">
                <form action="">
                  <div class="forminput">
                    <input type="email" placeholder="Email*">
                    <div class="msgerror">
                      <p>Email Should use @</p>
                    </div>
                  </div>
                  <div class="forminput">
                    <input type="password" placeholder="Password*">
                    <div class="msgerror">
                      <p>Email Should use @</p>
                    </div>
                  </div>
                </form>
                <div class="regist">
                  <h1>Belum punya Akun?</h1>
                  <p @click="daftar">Daftar</p>
                </div>
              </div>
            <!--  -->
            <!-- Code === 1 -->
              <div v-if="code === 1">
                <form action="">
                  <div class="forminput first">
                    <input type="text" placeholder="First Name*">
                    <input type="text" placeholder="First Name*">
                  </div>
                  <div class="forminput">
                    <input type="email" placeholder="Email*">
                    <div class="msgerror">
                      <p>Email Should use @</p>
                    </div>
                  </div>
                  <div class="forminput">
                    <input type="password" placeholder="Password*">
                    <div class="msgerror">
                      <p>Email Should use @</p>
                    </div>
                  </div>
                </form>
                <div class="regist">
                  <h1>Sudah punya Akun?</h1>
                  <p @click="masuk">Masuk</p>
                </div>
              </div>
            <!--  -->
          </div>
        </div>
        <div class="left">
          <div class="head">
            <h1>Order Summary</h1>
          </div>
          <div class="boxorder">
            <!-- Card -->
              <div class="cards" v-for="i in 10" :key="i.id">
                <div class="imagenum">
                  <p>1</p>
                </div>
                <div class="aseas">
                  <div class="tiket">
                    <p>Judul Tiket</p>
                  </div>
                  <div class="price">
                    <p>Free</p>
                  </div>
                </div>
              </div>
            <!--  -->
          </div>
          <div class="line"></div>
          <div class="prices">
            <p>Total</p>
            <h1>$0.00</h1>
          </div>
          <div class="butons">
            <button class="btn btn-primary">Submit</button>
          </div>
          <div class="bck">
            <router-link to="/ticket">Back</router-link>
          </div>
        </div>
      </div>
    <!--  -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      code: 1,
    };
  },
  methods: {
    daftar() {
      this.code = 1;
      console.log('asolele');
    },
    masuk() {
      this.code = 2;
      console.log('asolele');
    },
  },
};
</script>

<style lang="scss" scoped>
  .contains{
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    .navbars{
      width: 100%;
      height: 70px;
      background: #152955;
      display: flex;
      align-items: center;
      .logos img{
        width: 150px;
        margin-left: 30px;
      }
    }
    .content{
      width: 100%;
      height: calc(100% - 70px);
      // background: #f1f2f6;
      display: flex;
      .right{
        width: 70%;
        height: 100%;
        background: #f1f2f6;
        padding: 20px 70px;
        display: flex;
        flex-direction: column;
        align-items: center;
        .judul{
          width: 100%;
          display: flex;
          flex-direction: column;
          align-items: center;
          margin-bottom: 40px;
          h1{
            font-size: 26px;
          }
          p{
            font-size: 14px;
          }
        }
        .box{
          width: 80%;
          height: auto;
          background: white;
          border-radius: 10px;
          display: flex;
          flex-direction: column;
          padding: 20px 40px;
          .head{
            width: 100%;
            display: flex;
            justify-content: center;
            margin-bottom: 20px;
            h1{
              font-size: 32px;
              color: #666;
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
            .first{
              display: flex;
              justify-content: space-between;
              margin: 20px 0;
              input{
                width: 48% !important;
              }
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
            p{
              margin: 0;
              text-decoration: none;
              color: #0076d6;
              cursor: pointer;
            }
          }
        }
      }
      .left{
        width: 30%;
        height: 100%;
        background: white;
        box-shadow: 0 8px 30px 0 rgba(0, 0, 0, 0.06);
        padding: 40px;
        .head{
          width: 100%;
          h1{
            font-size: 30px;
          }
        }
        .boxorder{
          width: 100%;
          height: 260px;
          overflow-y: auto;
          margin: 20px 0 40px 0;
          background: white;
          .cards{
            width: 98%;
            height: 70px;
            margin: 10px 0;
            background: white;
            border: 1px solid #e9ecf6;
            border-radius: 4px;
            box-shadow: 0 2px 10px 0 rgba(0, 0, 0, 0.05);
            display: flex;
            // justify-content: space-between;
            align-items: center;
            p{
              margin: 0;
            }
            .imagenum{
              width: 35px;
              height: 35px;
              border-radius: 100%;
              background: navy;
              display: flex;
              align-items: center;
              justify-content: center;
              margin: 0 10px;
              p{
                color: white;
                font-weight: bold;
                font-size: 20px;
              }
            }
            .aseas{
              display: flex;
              justify-content: space-between;
              width: 80%;
              .price{
                p{
                  font-weight: bold;
                  color: #666;
                }
              }
            }
          }
        }
        .line{
          width: 100%;
          height: 2px;
          background: rgb(218, 223, 235);
          margin-bottom: 20px;
        }
        .prices{
          display: flex;
          justify-content: space-between;
          p{
            font-size: 18px;
          }
          h1{
            font-size: 18px;
            color: #406ae8;
          }
        }
        .butons{
          width: 100%;
          display: flex;
          justify-content: center;
          button{
            width: 100%;
            padding: 10px 0;
          }
        }
        .bck{
          width: 100%;
          display: flex;
          justify-content: center;
          margin: 10px 0;
          a{
          }
        }
      }
    }
  }
</style>
