<template>
	<view class="content">
		<form class="app-update-pv">
			
									<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">出售编号</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.chushoubianhao" v-model="ruleForm.chushoubianhao" placeholder="出售编号"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">出售商品名称</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.chushoushangpinmingcheng" v-model="ruleForm.chushoushangpinmingcheng" placeholder="出售商品名称"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0","borderStyle":"solid","height":"108rpx"}' class="cu-form-group select">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">商品类别</view>
				<picker @change="shangpinleibieChange" :value="shangpinleibieIndex" :range="shangpinleibieOptions">
					<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' class="uni-input">{{ruleForm.shangpinleibie?ruleForm.shangpinleibie:"请选择商品类别"}}</view>
				</picker>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0.1)","borderColor":"#ccc","margin":"0 0 20rpx 0","borderWidth":"0","borderStyle":"solid","height":"160rpx"}' class="cu-form-group" @tap="shangpintupianTap" :class='right == "left"?"":"active"'>
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(51, 51, 51, 1)","textAlign":"center"}' class="title">商品图片</view>
				<view class="right-input" :style='{textAlign:"right"}' style="padding:0">
					<image :style='{"width":"120rpx","boxShadow":"0 0 8rpx rgba(0,0,0,.3)","borderRadius":"40rpx","textAlign":"right","height":"120rpx"}' class="avator" v-if="ruleForm.shangpintupian" :src="ruleForm.shangpintupian" mode="aspectFill"></image>
					<image :style='{"width":"120rpx","boxShadow":"0 0 8rpx rgba(0,0,0,.3)","borderRadius":"40rpx","textAlign":"right","height":"120rpx"}' class="avator" v-else src="../../static/gen/upload.png" mode="aspectFill"></image>
				</view>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">商品品牌</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.shangpinpinpai" v-model="ruleForm.shangpinpinpai" placeholder="商品品牌"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">商品规格</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.shangpinguige" v-model="ruleForm.shangpinguige" placeholder="商品规格"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">新旧程度</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.xinjiuchengdu" v-model="ruleForm.xinjiuchengdu" placeholder="新旧程度"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">原价</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.yuanjia" v-model="ruleForm.yuanjia" placeholder="原价"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">出售价格</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.chushoujiage" v-model="ruleForm.chushoujiage" placeholder="出售价格"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">数量</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.shuliang" v-model="ruleForm.shuliang" placeholder="数量"></input>
			</view>
																					<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0","borderStyle":"solid","height":"108rpx"}' class="cu-form-group select">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">交易方式</view>
				<picker @change="jiaoyifangshiChange" :value="jiaoyifangshiIndex" :range="jiaoyifangshiOptions">
					<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' class="uni-input">{{ruleForm.jiaoyifangshi?ruleForm.jiaoyifangshi:"请选择交易方式"}}</view>
				</picker>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0","borderStyle":"solid","height":"108rpx"}' class="cu-form-group select">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">发布时间</view>
				<picker mode="date" :value="ruleForm.fabushijian" @change="fabushijianChange">
					<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' class="uni-input">{{ruleForm.fabushijian?ruleForm.fabushijian:"请选择发布时间"}}</view>
				</picker>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0","borderStyle":"solid","height":"108rpx"}' class="cu-form-group select">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">用户名</view>
				<picker @change="yonghumingChange" :value="yonghumingIndex" :range="yonghumingOptions">
					<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' class="uni-input">{{yonghumingOptions[yonghumingIndex]}}</view>
				</picker>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">姓名</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.xingming" v-model="ruleForm.xingming" placeholder="姓名"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">手机</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.shouji" v-model="ruleForm.shouji" placeholder="手机"></input>
			</view>
																																													
			<!-- 否 -->
 
			
			          				          				          				          				          				          				          				          				          				          				          				          				          				          				          				          				          				          				          				          							
			          				          				          				          				          				          				          				          				          				          				          				<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0 0 0 0","borderWidth":"0","borderStyle":"solid","height":"308rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">商品详情</view>
				<textarea :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"280rpx"}' v-model="ruleForm.shangpinxiangqing" placeholder="商品详情"></textarea>
			</view>
						          				          				          				          				          				          				          				          				          							
			<view class="btn">
				<button :style='{"boxShadow":"0 0 0px rgba(0,0,0,0) inset","backgroundColor":"rgba(113, 186, 0, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"8rpx","color":"#fff","borderWidth":"2rpx","width":"90%","fontSize":"32rpx","borderStyle":"solid","height":"80rpx"}' @tap="onSubmitTap" class="bg-red">提交</button>
			</view>
		</form>

																																																																																					
	</view>
</template>

<script>
	import wPicker from "@/components/w-picker/w-picker.vue";

	export default {
		data() {
			return {
				ruleForm: {
												chushoubianhao: '',
																chushoushangpinmingcheng: '',
																shangpinleibie: '',
																shangpintupian: '',
																shangpinpinpai: '',
																shangpinguige: '',
																xinjiuchengdu: '',
																yuanjia: '',
																chushoujiage: '',
																shuliang: '',
																shangpinxiangqing: '',
																jiaoyifangshi: '',
																fabushijian: '',
																yonghuming: '',
																xingming: '',
																shouji: '',
																sfsh: '',
																shhf: '',
																clicknum: '',
																userid: '',
												},
																												shangpinleibieOptions: [],
				shangpinleibieIndex: 0,
																																																																																jiaoyifangshiOptions: [],
				jiaoyifangshiIndex: 0,
																								yonghumingOptions: [],
				yonghumingIndex: 0,
																																																												// 登陆用户信息
				user: {},
                                ro:{
                                   chushoubianhao : false,
                                   chushoushangpinmingcheng : false,
                                   shangpinleibie : false,
                                   shangpintupian : false,
                                   shangpinpinpai : false,
                                   shangpinguige : false,
                                   xinjiuchengdu : false,
                                   yuanjia : false,
                                   chushoujiage : false,
                                   shuliang : false,
                                   shangpinxiangqing : false,
                                   jiaoyifangshi : false,
                                   fabushijian : false,
                                   yonghuming : false,
                                   xingming : false,
                                   shouji : false,
                                   sfsh : false,
                                   shhf : false,
                                   clicknum : false,
                                   userid : false,
                                },
			}
		},
		components: {
			wPicker
		},
		computed: {
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
					},
		async onLoad(options) {
			let table = uni.getStorageSync("nowTable");
			// 获取用户信息
			let res = await this.$api.session(table);
			this.user = res.data;
			
						// ss读取
																																																																																																																														
																								// 下拉框
			res = await this.$api.option(`shangpinfenlei`,`shangpinleibie`,{});
			this.shangpinleibieOptions = res.data;
																																																												// 自定义下拉框值
			this.jiaoyifangshiOptions = "线上,线下".split(',')
																		// 下2
			res = await this.$api.option(`yonghu`,`yonghuming`,{});
			this.yonghumingOptions = res.data;
																																													
			// 如果有登陆，获取登陆后保存的userid
			this.ruleForm.userid = uni.getStorageSync("userid")
			if (options.refid) {
				// 如果上一级页面传递了refid，获取改refid数据信息
				this.ruleForm.refid = options.refid;
				this.ruleForm.nickname = uni.getStorageSync("nickname");
			}
			// 如果是更新操作
			if (options.id) {
				this.ruleForm.id = options.id;
				// 获取信息
				res = await this.$api.info(`xinxifabu`, this.ruleForm.id);
				this.ruleForm = res.data;
			}
			// 跨表
			if(options.cross){
				var obj = uni.getStorageSync('crossObj');
				for (var o in obj){
					if(o=='chushoubianhao'){
					this.ruleForm.chushoubianhao = obj[o];
					this.ro.chushoubianhao = true;
					continue;
					}
					if(o=='chushoushangpinmingcheng'){
					this.ruleForm.chushoushangpinmingcheng = obj[o];
					this.ro.chushoushangpinmingcheng = true;
					continue;
					}
					if(o=='shangpinleibie'){
					this.ruleForm.shangpinleibie = obj[o];
					this.ro.shangpinleibie = true;
					continue;
					}
					if(o=='shangpintupian'){
					this.ruleForm.shangpintupian = obj[o];
					this.ro.shangpintupian = true;
					continue;
					}
					if(o=='shangpinpinpai'){
					this.ruleForm.shangpinpinpai = obj[o];
					this.ro.shangpinpinpai = true;
					continue;
					}
					if(o=='shangpinguige'){
					this.ruleForm.shangpinguige = obj[o];
					this.ro.shangpinguige = true;
					continue;
					}
					if(o=='xinjiuchengdu'){
					this.ruleForm.xinjiuchengdu = obj[o];
					this.ro.xinjiuchengdu = true;
					continue;
					}
					if(o=='yuanjia'){
					this.ruleForm.yuanjia = obj[o];
					this.ro.yuanjia = true;
					continue;
					}
					if(o=='chushoujiage'){
					this.ruleForm.chushoujiage = obj[o];
					this.ro.chushoujiage = true;
					continue;
					}
					if(o=='shuliang'){
					this.ruleForm.shuliang = obj[o];
					this.ro.shuliang = true;
					continue;
					}
					if(o=='shangpinxiangqing'){
					this.ruleForm.shangpinxiangqing = obj[o];
					this.ro.shangpinxiangqing = true;
					continue;
					}
					if(o=='jiaoyifangshi'){
					this.ruleForm.jiaoyifangshi = obj[o];
					this.ro.jiaoyifangshi = true;
					continue;
					}
					if(o=='fabushijian'){
					this.ruleForm.fabushijian = obj[o];
					this.ro.fabushijian = true;
					continue;
					}
					if(o=='yonghuming'){
					this.ruleForm.yonghuming = obj[o];
					this.ro.yonghuming = true;
					continue;
					}
					if(o=='xingming'){
					this.ruleForm.xingming = obj[o];
					this.ro.xingming = true;
					continue;
					}
					if(o=='shouji'){
					this.ruleForm.shouji = obj[o];
					this.ro.shouji = true;
					continue;
					}
					if(o=='clicknum'){
					this.ruleForm.clicknum = obj[o];
					this.ro.clicknum = true;
					continue;
					}
					if(o=='userid'){
					this.ruleForm.userid = obj[o];
					this.ro.userid = true;
					continue;
					}
				}
			}
			this.styleChange()
		},
		methods: {
			styleChange() {
				this.$nextTick(()=>{
					// document.querySelectorAll('.app-update-pv .cu-form-group .uni-input-input').forEach(el=>{
					//   el.style.backgroundColor = this.addUpdateForm.input.content.backgroundColor
					// })
				})
			},
																																																																																										// 下二随
			async yonghumingChange (e) {
				this.yonghumingIndex = e.target.value
				this.ruleForm.yonghuming = this.yonghumingOptions[this.yonghumingIndex]
				let res = await this.$api.follow(`yonghu`, `yonghuming`,{
					columnValue: this.ruleForm.yonghuming
				});
																																																																																																																												if(res.data.xingming){
					this.ruleForm.xingming = res.data.xingming
				}
																if(res.data.shouji){
					this.ruleForm.shouji = res.data.shouji
				}
																																											},
																																										
			// 多级联动参数
																																																																																																																														
																																																																																	fabushijianChange(e) {
				this.ruleForm.fabushijian = e.target.value;
				this.$forceUpdate();
			},
																																																
																																																																																																																											
																					// 下拉变化
			shangpinleibieChange(e) {
				this.shangpinleibieIndex = e.target.value
				this.ruleForm.shangpinleibie = this.shangpinleibieOptions[this.shangpinleibieIndex]
			},
																																																												// 下拉变化
			jiaoyifangshiChange(e) {
				this.jiaoyifangshiIndex = e.target.value
				this.ruleForm.jiaoyifangshi = this.jiaoyifangshiOptions[this.jiaoyifangshiIndex]
			},
																																																						
																																				shangpintupianTap() {
				let _this = this;
				this.$api.upload(function(res) {
					_this.ruleForm.shangpintupian = _this.$base.url + 'upload/' + res.file;
					_this.$forceUpdate();
					_this.$nextTick(()=>{
						_this.styleChange()
					})
				});
			},
																																																																																																																																																									
			getUUID () {
				return new Date().getTime();
			},
			async onSubmitTap() {
																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																												if((!this.ruleForm.chushoubianhao)){
					this.$utils.msg(`出售编号不能为空`);
					return
				}
																																												if((!this.ruleForm.chushoushangpinmingcheng)){
					this.$utils.msg(`出售商品名称不能为空`);
					return
				}
																																												if((!this.ruleForm.shangpinleibie)){
					this.$utils.msg(`商品类别不能为空`);
					return
				}
																																																																																																																																																																																																if(this.ruleForm.yuanjia&&(!this.$validate.isIntNumer(this.ruleForm.yuanjia))){
					this.$utils.msg(`原价应输入整数`);
					return
				}
																																								if((!this.ruleForm.chushoujiage)){
					this.$utils.msg(`出售价格不能为空`);
					return
				}
												if(this.ruleForm.chushoujiage&&(!this.$validate.isIntNumer(this.ruleForm.chushoujiage))){
					this.$utils.msg(`出售价格应输入整数`);
					return
				}
																																																																																																																if((!this.ruleForm.jiaoyifangshi)){
					this.$utils.msg(`交易方式不能为空`);
					return
				}
																																																																																																																																																																								if(this.ruleForm.shouji&&(!this.$validate.isMobile(this.ruleForm.shouji))){
					this.$utils.msg(`手机应输入手机格式`);
					return
				}
																																																																																																								if(this.ruleForm.clicknum&&(!this.$validate.isIntNumer(this.ruleForm.clicknum))){
					this.$utils.msg(`点击次数应输入整数`);
					return
				}
																																																																								if(this.ruleForm.id){
					await this.$api.update(`xinxifabu`, this.ruleForm);
				}else{
					await this.$api.add(`xinxifabu`, this.ruleForm);
				}
				this.$utils.msgBack('提交成功');
			},
			optionsChange(e) {
				this.index = e.target.value
			},
			bindDateChange(e) {
				this.date = e.target.value
			},
			getDate(type) {
				const date = new Date();
				let year = date.getFullYear();
				let month = date.getMonth() + 1;
				let day = date.getDate();
				if (type === 'start') {
					year = year - 60;
				} else if (type === 'end') {
					year = year + 2;
				}
				month = month > 9 ? month : '0' + month;;
				day = day > 9 ? day : '0' + day;
				return `${year}-${month}-${day}`;
			},
			toggleTab(str) {
				this.$refs[str].show();
			}
		}
	}
</script>

<style lang="scss" scoped>
	.container {
		padding: 20upx;
	}
	
	.content:after {
		position: fixed;
		top: 0;
		right: 0;
		left: 0;
		bottom: 0;
		content: '';
				background-image: url(http://codegen.caihongy.cn/20210329/bac17293dec74a61b63867efe3bb6be6.png);
				background-attachment: fixed;
		background-size: cover;
		background-position: center;
	}

	textarea {
		border: 1upx solid #EEEEEE;
		border-radius: 20upx;
		padding: 20upx;
	}

	.title {
		width: 180upx;
	}

	.avator {
		width: 150upx;
		height: 60upx;
	}

	.right-input {
		flex: 1;
		text-align: left;
		padding: 0 24upx;
	}
	
	.cu-form-group.active {
		justify-content: space-between;
	}
	
	.btn {
	  display: flex;
	  align-items: center;
	  justify-content: center;
	  flex-wrap: wrap;
	  padding: 20upx 0;
	}
	
	.cu-form-group {
		padding: 0 24upx;
		background-color: transparent;
		min-height: inherit;
	}
	
	.cu-form-group+.cu-form-group {
		border: 0;
	}
	
	.cu-form-group uni-input {
		padding: 0 30upx;
	}
	
	.uni-input {
		padding: 0 30upx;
	}
	
	.cu-form-group uni-textarea {
		padding: 30upx;
		margin: 0;
	}
	
	.cu-form-group uni-picker::after {
		line-height: 80rpx;
	}
	
	.select .uni-input {
		line-height: 80rpx;
	}
	
	.input .right-input {
		line-height: 80rpx;
	}
</style>
