<template>
  <div class="linkageOptions_">
    <p class="L_title">定制方案CUSTOMIZATION SCHEME</p>
    <div class="lf_kuang">
      <span>选择方案</span>
      <p>1.0原液配方体系</p>
      <img src="http://unesmall.b0.upaiyun.com/unes_pro/F04.png"/>
      <div class="pfxuanx">
        <div>
          <input name="linkageType1" type="checkbox" value="1_"/><label>补水保湿配方</label>
        </div>
        <div>
          <input name="linkageType1" type="checkbox" value="2_"/><label>美白淡斑配方</label>
        </div>
        <div>
          <input name="linkageType1" type="checkbox" value="3_"/><label>毛孔修护配方</label>
        </div>
        <div>
          <input name="linkageType1" type="checkbox" value="4_"/><label>祛痘消印配方</label>
        </div>
        <div>
          <input name="linkageType1" type="checkbox" value="5_"/><label>舒缓修护配方</label>
        </div>
        <div>
          <input name="linkageType1" type="checkbox" value="6_"/><label>紧致淡纹配方</label>
        </div>
      </div>
      <div class="clear_"></div>
    </div>
    <div class="lf_kuang">
      <span>选择方案</span>
      <p>2.0活性态配方体系</p>
      <img src="http://unesmall.b0.upaiyun.com/unes_pro/F04.png"/>
      <div  class="pfxuanx zhujibia" >
        <div>
          <input name="linkageType2" type="checkbox" value="7_"/><label>激素脸配方</label>
        </div>
        <div>
          <input name="linkageType2" type="checkbox" value="8_"/><label>美白淡斑配方</label>
        </div>
        <div>
          <input name="linkageType2" type="checkbox" value="9_"/><label>紧致淡纹配方</label>
        </div>
        <div>
          <input name="linkageType2" type="checkbox" value="10_"/><label>红血丝配方</label>
        </div>
        <div>
          <input name="linkageType2" type="checkbox" value="11_"/><label>敏感修护配方</label>
        </div>
      </div>
      <div class="clear_"></div>
    </div>
    <!-- ------------------------------------------------------------------------------------------------------------- -->

    <p class="L_title">产品配方PRODUCT FORMULA</p>
    <div class="P_kuang">
      <div>
        原液理肤配方
      </div>
      <div>
        <div class="dangepeif yuanyelifupeifang" v-for="(val,index) in yylfpf_" :key="index">
          <input class="xianshi" name="linkageType3" type="checkbox" :value="val.id"/><label>{{val.name}}</label>
          <div class="xiangqing_" v-if="pfguodu_.indexOf(val.id)>=0 || zixuanarr.indexOf(val.id)>=0 || monrenarr.indexOf(val.id)>=0 ">
            <p style="font-size:12px;font-weight: bold;line-height:20px;">产品成分</p>
            <p v-for="(v,i) in val.formula.ingredients" :key="i">
              <span style="font-family: 'Helvetica Neue',Helvetica,Arial,sans-serif;font-size: 14px;line-height: 1.42857143;color: #333;">{{v.name}}:</span>
              <span type="text" style="font-size:12px;margin-top: 0px;width: 40px;height: 15px;border: none;outline: none;border-bottom: 1px solid #dddddd;vertical-align: middle;">{{v.defaultPer+'%'}}</span>
            </p>
          </div>
        </div>
      </div>
      <div class="clear_"></div>
    </div>
    <!-- ------------------------------------------------------------------------------------------------------------- -->

    <div class="P_kuang">
      <div>
        活性肽<br/>配方
      </div>
      <div>
        <div class="dangepeif huoxingtaipeifang" v-for="(val,index) in hxtpf_" :key="index">
          <input class="xianshi" name="linkageType4" type="checkbox" :value="val.id"/><label>{{val.name}}</label>
        </div>
      </div>
      <div class="clear_"></div>
    </div>
    <!-- ------------------------------------------------------------------------------------------------------------- -->

    <div class="P_kuang">
      <div>
        日常护理搭配
      </div>
      <div class="richanghulidapei">
        <div class="" v-for="(val,index) in rchl_" :key="index">
          <input class="xianshi" name="linkageType4"  type="checkbox" :value="val.id"/><label>{{val.name}}</label>
        </div>
      </div>
      <div class="clear_"></div>
    </div>
    <!-- ------------------------------------------------------------------------------------------------------------- -->

    <div class="P_kuang">
      <div>
        周护理<br/>搭配
      </div>
      <div class="zhouhulidapei">
        <div class="" v-for="(val,index) in zhl_" :key="index">
          <input class="xianshi" name="linkageType4"  type="checkbox" :value="val.id"/><label>{{val.name}}</label>
        </div>
        <div class="clear_"></div>
      </div>
      <div class="clear_"></div>
    </div>
    <!-- ------------------------------------------------------------------------------------------------------------- -->

  </div>
</template>

<script>
export default {
  props:[ "linOpVal" ],
  data() {
    return {
      // 配方数据
      strVal_:'',
      // 配方名字字符串
      nameStr:'',
      yylfpf_:'',
      hxtpf_:'',
      rchl_:'',
      zhl_:'',
      pf_:[
        [18,25],
        [18,19,20],
        [18,20,23],
        [18,23,24],
        [18,21,25],
        [18,21,22],
        [56,55,49],
        [46,148],
        [50,55],
        [49,56],
        [56,55,49]
      ],
      zixuanarr:[],
      pfguodu_:[],
      monrenarr:[],
      morenpeifang:'',
      jishu:0
    }
  },
  watch: {
    linOpVal: {
　　　handler(newValue, oldValue) {
        var this_=this;
        this.yylfpf_=newValue.yylfpf;
        this.hxtpf_=newValue.hxtpf;
        this.rchl_=newValue.rchl;
        this.zhl_=newValue.zhl;
        this.monrenarr=newValue.morenxians.zixuanarr;
        this.morenpeifang=newValue.morenxians.morenpeifang;
        this.nameStr=newValue.morenxians.morenpeifang;

        if(this.monrenarr.length>0){
          this.zixuanarr=[];
        }else{
          this.zixuanarr=[140,141,142,143,144,145,146];
        }

        this_.pfchecked_();

        if(this.jishu==0){
          setTimeout(function(){
            this_.morenxianshi1_();
            this_.allarr();
            this_.jishu++;
          },600);
        }
　　　},
　　　deep: true
　　}
  },
  mounted(){
    this.allarr();
  },
  methods:{
    pfchecked_:function(){
      var this_=this;
      var cishu=-1;
      // 自选配方
      $(".pfxuanx>div>input").change(function(){
        this_.monrenarr.length=0;
        var num_=parseInt($(this).attr('value'));
        var thisi_=$(this);
        // 单选选中
        $(".pfxuanx>div>input").not(this).each(function(){
          if(num_==7 || num_==11){
            liandong($(this),5);
          }else if(num_==8){
            liandong($(this),2);
          }else if(num_==9){
            liandong($(this),6);
          }else if(num_==10){
            liandong($(this),5);
          }else{
            liandong($(this),-1);
          };
        });

        // 自选配方选中
        $(".dangepeif>input").each(function(){
          var i=parseInt($(this).attr('value'));
          if(this_.pfguodu_.indexOf(i)>=0 || this_.zixuanarr.indexOf(i)>=0){
            $(this).attr("checked","checked").prop("checked", true);
          }else{
            $(this).prop("checked", false).removeAttr("checked","checked");
          };
        });

        // 联动选中函数
        function liandong(that,number_){
          // 判断点击的选项是否为选中状态
          if(thisi_.is(":checked")){
            // 添加属性
            thisi_.attr("checked","checked").prop("checked", true);
            // 删除其兄弟属性
            thisi_.parent().siblings().children('input').prop("checked", false).removeAttr("checked","checked");

            // 参数大于0表示联动
            if(number_>=0){

              // 参数对应联动选项
              if (that.attr('value')==number_+'_'){
                // 设置联动对应选项为选中
                that.attr("checked","checked").prop("checked", true);
              }else{
                // 非对应选项设置为不选中
                if(that.attr('checked')){
                  that.prop("checked", false).removeAttr("checked","checked");
                }
              };
              // 配方
              this_.pfguodu_=this_.pf_[num_-1].concat(this_.pf_[number_-1],this_.zixuanarr);
            }else if(number_<0){
            // 参数小于0为非联动选项
              // 设置所有的联动选项为不选中并且删除属性
              that.prop("checked", false).removeAttr("checked","checked");
              // 配方
              this_.pfguodu_=this_.pf_[num_-1].concat(this_.zixuanarr);
            };
          }else{
            // 设置不选中并且删除属性
            thisi_.prop("checked", false).removeAttr("checked","checked");
            that.prop("checked", false).removeAttr("checked","checked");
            this_.pfguodu_=[];
          };
        };

        // 配方名字字符串ok
        var namearr=[];
        this_.nameStr='';
        $(".pfxuanx>div>input").each(function(){
          if($(this).is(":checked")){
            namearr.push(
              $(this).siblings('label').text()
            );
          }
        });
        for(var i=0;i<namearr.length;i++){
          this_.nameStr+=(i+1)+','+namearr[i];
          if((i+1)<namearr.length){
              this_.nameStr+=';';
          }
        };

        this_.allarr();
      });

      // ok
      setTimeout(function(){
        $(".xianshi").change(function(){
          if($(this).is(":checked")){
            this_.zixuanarr.push(
              parseInt($(this).attr('value'))
            );
            $(this).attr("checked","checked").prop("checked", true);
          }else{
            var val_a = parseInt($(this).attr('value'));
            var ind = this_.zixuanarr.indexOf(val_a);
            if(this_.zixuanarr[ind]==val_a){
              this_.zixuanarr.splice(ind,1);
            }

            var inde = this_.pfguodu_.indexOf(val_a);
            if(this_.pfguodu_[inde]==val_a){
              this_.pfguodu_.splice(inde,1);
            }

            var index = this_.monrenarr.indexOf(val_a);
            if(this_.monrenarr[index]==val_a){
              this_.monrenarr.splice(index,1);
            }

            $(this).prop("checked", false).removeAttr("checked","checked");
          }
          this_.allarr();
        });
      },600);

    },
    // 数据拼接字符串ok
    allarr:function(){
      var alla=[];
      var str='';
      var zjr=[this.yylfpf_,this.hxtpf_,this.rchl_,this.zhl_];

      $(".P_kuang>div>div>input").each(function(){
        if ($(this).is(":checked")){
          alla.push(parseInt($(this).attr('value')));
        };
      });

      //循环 总表单
      for(var i=0;i<zjr.length;i++){
        // 循环选中 formula
        for(var n=0;n<zjr[i].length;n++){
          // 判断是否选中
          if(alla.indexOf(zjr[i][n].id)>=0){
            // 字符串拼接id
            str+=zjr[i][n].id+'&';
            if(i==0){
              // 循环 ingredients 产品成份
              for(var m=0;m<zjr[i][n].formula.ingredients.length;m++){
                // 字符串拼接产品含量
                str+=zjr[i][n].formula.ingredients[m].name+":"+zjr[i][n].formula.ingredients[m].defaultPer;
                // 判断是否最后一个成份
                if(m+1<zjr[i][n].formula.ingredients.length){
                  str+=';';
                }else{
                  str+=',';
                }
              }
            }else{
                str+='无,';
            }
          }
        }
      };
      this.strVal_=str.slice(0,str.length-1);
    },
    // 默认显示ok
    morenxianshi1_:function(){
      var this_=this;
      $(".xianshi").each(function(){
        var i=parseInt($(this).attr('value'));
        if(this_.monrenarr.indexOf(i)>=0 || this_.zixuanarr.indexOf(i)>=0){
          $(this).attr("checked","checked").prop("checked", true);
        }else{
          if($(this).attr('checked')){
            $(this).prop("checked", false).removeAttr("checked","checked");
          }
        };
      });

      $(".pfxuanx>div>input").each(function(){
        var nastr=$(this).siblings('label').text();
        if(this_.morenpeifang){
          if(this_.morenpeifang.indexOf(nastr)>=0){
            $(this).attr("checked","checked").prop("checked", true);
          }
        }
      });
    }
  }
}
</script>

<style>
.L_title{
  margin: 25px 0;
  font-size: 17px;
  height: 20px;
  line-height: 20px;
  clear: both;
  text-align: left;
}
.lf_kuang{
  width:100%;
  height: 100px;
  display: flex;
  flex-direction:row;
  flex-wrap:wrap;
  justify-content:space-around;
  align-items:center;
}
.lf_kuang>p{
  cursor: pointer;
  line-height: 37px;
  text-align: center;
  width: 125px;
  height: 37px;
  background:#656565;
  color: #fff;
  position: relative;
}
.lf_kuang>div{
  width: 75%;
  height: 70px;
  display: flex;
  flex-direction:row;
  flex-wrap:wrap;
  align-content:space-around;
}
.lf_kuang>div>div{
  width:25%;
  height: auto;
  text-align: left;
}
.lf_kuang>img{
  width:18px;
  height:18px;
}
.P_kuang{
  width:100%;
  height: auto;
  margin-bottom: 25px;
}
.P_kuang>div:nth-child(1){
  float: left;
  width: 95px;
  height: 60px;
  border: 1px solid #969696;
  border-radius: 5px;
  font-size: 15px;
  color: #747474;
  text-align: center;
  padding: 13px 13px 0 13px;
  box-sizing: border-box;
}
.P_kuang>div:nth-child(2){
  width: 85%;
  height: auto;
  min-height: 60px;
  float: left;
  margin-left:25px;
  display: flex;
  flex-direction:row;
  flex-wrap:wrap;
  align-content:space-around;
}
.richanghulidapei,.zhouhulidapei{
  line-height: 60px;
}
.yuanyelifupeifang,.huoxingtaipeifang{
  line-height: 29px;
}

.P_kuang>div:nth-child(2)>div{
  width:20%;
  height: auto;
  text-align: left;
}
.xiangqing_{
  padding: 10px 0;
}
</style>
