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
    <div class="invoice">
      <h1>FRESCOllaboration Show (Brisia Jodie x Alif Rizky)</h1>
      <router-link to="/checkout">
        <button class="btn btn-primary">BELI TIKET</button>
      </router-link>
    </div>
    <div class="ticket">
      <div class="imgticket">
        <img src="https://s3-ap-southeast-1.amazonaws.com/loket-production-sg/images/banner/20200831194010_5f4cefaac1d09.jpg" alt="">
      </div>
      <div class="infoticket">
        <div class="judulticket">
          <h1>ANAKBRAND CLASS - MODUL 1 (BRAND STRATEGY) </h1>
        </div>
        <hr>
        <div class="agendaticket">
          <div class="selenggarakan">
            <h1>Diselenggarakan Oleh</h1>
            <div>
              <img src="https://s3-ap-southeast-1.amazonaws.com/loket-production-sg/images/organization/20200818181404_5f3bb7fc20283.png" alt="">
              <a href="#">Ideate.id</a>
            </div>
          </div>
          <div class="tglwkt">
            <h1>Tanggal & Waktu</h1>
            <p>29 Aug 2020 - 05 Sep 2020</p>
            <p>10:00 - 17:30 WIB</p>
          </div>
          <div class="lokasi">
            <h1>Lokasi</h1>
            <p>Event Online</p>
          </div>
        </div>
      </div>
    </div>
    <div class="deskticket">
      <div class="chooseopt">
        <div @click="desk" class="menuclick desk borbot">
          <h1>DESKRIPSI EVENT</h1>
        </div>
        <div @click="cate" class="menuclick cate">
          <h1>KATEGORI TIKET</h1>
        </div>
      </div>
      <!-- if 1 -->
      <div class="deskripsi" v-if="code === 1">
        <div class="juduldesk">
          <h1>DESKRIPSI EVENT</h1>
        </div>
        <div class="textdesk">
          <p>Brisia Jodie dan Alif Rizky atau biasa dikenal dengan Paijo
             akan tampil di Frescollaboration Show yang diadakan oleh Kopi
              Fresco! Alif Rizky yang dikenal sebagai content creator akan
               bersama Brisia Jodie dalam intimate session yang akan tampil
                di Frescollaboration Show pada 12 September 2020. Jangan
                 sampai ketinggalan penampilan dari mereka.</p>
        </div>
      </div>
      <div class="categori" v-if="code === 2">
        <div class="all" v-for="i in 3" :key="i.id">
          <div class="lefts">
            <span></span>
            <h1>28 Aug</h1>
          </div>
          <div class="rights">
            <div class="judulrights">
              <h1>2-Day Conference (4 Workshops)</h1>
            </div>
            <hr>
            <div class="dipright">
              <div class="infoasdeq">
                <p>Access to ANY ONE Workshop: 1. Design Sprint 2.
                   Product Research 3. UX Design 4. Product Design
                </p>
                <a href="#">Berakhir tanggal 05 September 2020 | 10:00</a>
              </div>
              <div class="pricer">
                <h1>GRATIS</h1>
              </div>
              <div class="buttons">
                <button @click="buy" class="btn btn-primary">BELI</button>
              </div>
              <div class="button">
                <div class="btn btn-primary" @click="kurang">-</div>
                <p>{{totalbuy}}</p>
                <div class="btn btn-primary" @click="tambah">+</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      code: 1,
      test: 2,
      totalbuy: 1,
    };
  },
  methods: {
    tambah() {
      this.totalbuy = 1;
      // console.log(this.totalbuy );
      // console.log(this.totalbuy);
    },
    buy() {
      document.querySelector('.button').style.display = 'flex';
      document.querySelector('.buttons').style.display = 'none';
    },
    cate() {
      document.querySelector('.desk').classList.remove('borbot');
      document.querySelector('.cate').classList.add('borbot');
      this.code = 2;
    },
    desk() {
      document.querySelector('.cate').classList.remove('borbot');
      document.querySelector('.desk').classList.add('borbot');
      this.code = 1;
    },
  },
};
</script>

<style lang="scss" scoped>
  .contains{
    // padding: 40px 0;
    display: flex;
    // justify-content: center;
    align-items: center;
    flex-direction: column;
    .navbars{
      width: 100%;
      height: 70px;
      background: #152955;
      display: flex;
      align-items: center;
      margin-bottom: 10px;
      .logos img{
        width: 150px;
        margin-left: 30px;
      }
    }
    .invoice{
      z-index: 2;
      display: flex;
      align-items: center;
      justify-content: space-between;
      position: fixed;
      bottom: 0;
      width: 100%;
      height: 100px;
      background: whitesmoke;
      h1{
        font-weight: bolder;
        font-size: 28px;
        color: #686868;
        margin-left: 200px;
      }
      .btn{
        padding: 10px 25px;
        margin-right: 30px;
      }
    }
    .ticket{
      width: 900px;
      display: flex;
      flex-direction: column;
      border-radius: 7px;
      border: 2px solid #d7d7d7;
      margin-bottom: 60px;
      .imgticket{
        img{
          width: 100%;
          border-top-left-radius: 7px;
          border-top-right-radius: 7px;
        }
      }
      .infoticket{
        padding: 25px 40px;
        .judulticket{
          h1{
            font-size: 32px;
            width: 100%;
            overflow: hidden;
            white-space: nowrap;
            text-overflow: ellipsis;
            color: #686868;
          }
        }
        .agendaticket{
          display: flex;
          justify-content: space-between;
          h1{
            color: rgb(88, 88, 88);
            font-size: 18px;
            font-weight: bolder;
            margin-bottom: 25px;
          }
          p{
            color: #a7a7a7;
            font-size: 16px;
            margin: 0;
            margin-bottom: 10px;
          }
          img{
            width: 70px;
            height: 70px;
            border-radius: 100%;
          }
          a{
            text-decoration: none;
            font-size: 18px;
            margin-left: 15px;
          }
        }
      }
    }
    .deskticket{
      width: 900px;
      .chooseopt{
        display: flex;
        display: flex;
        justify-content: space-around;
        width: 100%;
        margin-bottom: 50px;
        .menuclick{
          cursor: pointer;
          display: flex;
          justify-content: center;
          width: 50%;
          padding-bottom: 10px;
          border-bottom: 2px solid #d7d7d7;
          h1{
            font-size: 15px;
            color: #999;
            font-weight: bold;
          }
        }
        .menuclick:hover{
          h1{

          color: rgb(26, 24, 24) !important;
          }
        }
      }
      .deskripsi{
        margin-bottom: 100px;
        .juduldesk{
          margin-bottom: 25px;
          h1{
            font-weight: bold;
            font-size: 18px;
            color: #666;
          }
        }
        .textdesk{
          color: #777;
          font-weight: normal;
          font-size: 16px;
        }
      }
      .categori{
        margin-bottom: 150px;
        .all{
          width: 100%;
          height: 200px;
          border: 1px solid #dadde6;
          border-radius: 7px;
          display: flex;
          margin: 10px 0;
          .lefts{
            width: 24%;
            border-right: 2px dashed #dadde6;
            height: 100%;
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            h1{
              color: #999;
            }
            span{
              position: absolute;
              width: 30px;
              height: 30px;
              background: white;
              border-radius: 100%;
              left: -15px;
              border-right: 2px solid #dadde6;
            }
          }
          .lefts::before,{
            content: '';
            width: 30px;
            height: 30px;
            position: absolute;
            background: white;
            border-radius: 50%;
            right: -15px;
            top: -15px;
            border-bottom: 1px solid #c2c6d1;
          }
          .lefts::after{
            content: '';
            width: 30px;
            height: 30px;
            position: absolute;
            background: white;
            border-radius: 50%;
            right: -15px;
            bottom: -15px;
            border-top: 1px solid #c2c6d1;
          }
          .rights{
            width: 76%;
            padding: 20px 15px;
            .judulrights{
              width: 100%;
            }
            h1{
              color: #686868;
              font-weight: bold;
              font-size: 22px;
            }
            .dipright{
              display: flex;
              .infoasdeq{
                p{
                  max-width: 430px;
                  color: #666;
                }
              }
            }
            .pricer{
              align-self: center;
              margin: 0 15px;
              h1{
                margin: 0;
              }
            }
            .buttons{
              display: flex;
              align-items: center;
              button{
                padding: 5px 30px;
                border-radius: 10px;
              }
            }
            .button{
              display: none;
              align-items: center;
              justify-content: center;
              p{
                margin: 0 10px;
              }
              .btn{
                padding: 5px 15px;
                border-radius: 10px;
                font-weight: bolder;
                font-size: 18px;
              }
            }
            .buy{
              align-self: center;
              padding: 5px 35px;
            }
          }
        }
      }
    }
  }
  .btn{
    border-radius: 20px;
    // background: transparent;
    // color: black;
    // border: 1px solid black;
  }
// asdasd
  .fl-left{float: left}

.fl-right{float: right}

.container
{
  width: 90%;
  margin: 100px auto
}

.row{overflow: hidden}

.card
{
  display: table-row;
  width: 100%;
  background-color: #fff;
  color: #989898;
  margin-bottom: 10px;
  font-family: 'Oswald', sans-serif;
  text-transform: uppercase;
  border-radius: 4px;
  position: relative
}

.card + .card{margin-left: 2%}

.date
{
  display: table-cell;
  width: 25%;
  position: relative;
  text-align: center;
  border-right: 2px dashed #dadde6
}

.date:before
{
  content: "";
  display: block;
  width: 30px;
  height: 30px;
  background-color: white;
  position: absolute;
  top: -17px ;
  right: -15px;
  z-index: 1;
  border-radius: 50%;
  border-bottom: 1px solid rgba(0,0,0,.125);
}
.date:after{
  content: "";
  display: block;
  width: 30px;
  height: 30px;
  background-color: white;
  position: absolute;
  top: -15px ;
  right: -15px;
  z-index: 1;
  border-radius: 50%;
  border-top: 1px solid rgba(0,0,0,.125);
}

.date:after
{
  top: auto;
  bottom: -15px
}

.date time
{
  display: block;
  position: absolute;
  top: 50%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%)
}

.date time span{display: block}

.date time span:first-child
{
  color: #2b2b2b;
  font-weight: 600;
  font-size: 250%
}

.date time span:last-child
{
  text-transform: uppercase;
  font-weight: 600;
  margin-top: -10px
}

.card-cont
{
  display: table-cell;
  width: 75%;
  font-size: 85%;
  padding: 10px 10px 30px 50px
}

.card-cont h3
{
  color: #3C3C3C;
  font-size: 130%
}

.row:last-child .card:last-of-type .card-cont h3
{
  text-decoration: line-through
}

.card-cont > div
{
  display: table-row
}

.card-cont .even-date i,
.card-cont .even-info i,
.card-cont .even-date time,
.card-cont .even-info p
{
  display: table-cell
}

.card-cont .even-date i,
.card-cont .even-info i
{
  padding: 5% 5% 0 0
}

.card-cont .even-info p
{
  padding: 30px 50px 0 0
}

.card-cont .even-date time span
{
  display: block
}

.card-cont a
{
  display: block;
  text-decoration: none;
  width: 80px;
  height: 30px;
  background-color: #D8DDE0;
  color: #fff;
  text-align: center;
  line-height: 30px;
  border-radius: 2px;
  position: absolute;
  right: 10px;
  bottom: 10px
}

.row:last-child .card:first-child .card-cont a
{
  background-color: #037FDD
}

.row:last-child .card:last-child .card-cont a
{
  background-color: #F8504C
}

@media screen and (max-width: 860px)
{
  .card
  {
    display: block;
    float: none;
    width: 100%;
    margin-bottom: 10px
  }

  .card + .card{margin-left: 0}

  .card-cont .even-date,
  .card-cont .even-info
  {
    font-size: 75%
  }
}
// asdasd
  .borbot{
    border-bottom: 3px solid #e36a35 !important;
  }
</style>
