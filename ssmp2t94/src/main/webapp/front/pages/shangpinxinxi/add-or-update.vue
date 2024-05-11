<template>
	<view class="content">
		<form class="app-update-pv">
			
									<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">商品编号</view>
				<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' class="right-input">
					{{ruleForm.shangpinbianhao}}
				</view>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">商品名称</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.shangpinmingcheng" v-model="ruleForm.shangpinmingcheng" placeholder="商品名称"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0","borderStyle":"solid","height":"108rpx"}' class="cu-form-group select">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">商品类别</view>
				<picker @change="shangpinleibieChange" :value="shangpinleibieIndex" :range="shangpinleibieOptions">
					<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' class="uni-input">{{ruleForm.shangpinleibie?ruleForm.shangpinleibie:"请选择商品类别"}}</view>
				</picker>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0.1)","borderColor":"#ccc","margin":"0 0 20rpx 0","borderWidth":"0","borderStyle":"solid","height":"160rpx"}' class="cu-form-group" @tap="tupianTap" :class='right == "left"?"":"active"'>
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(51, 51, 51, 1)","textAlign":"center"}' class="title">图片</view>
				<view class="right-input" :style='{textAlign:"right"}' style="padding:0">
					<image :style='{"width":"120rpx","boxShadow":"0 0 8rpx rgba(0,0,0,.3)","borderRadius":"40rpx","textAlign":"right","height":"120rpx"}' class="avator" v-if="ruleForm.tupian" :src="ruleForm.tupian" mode="aspectFill"></image>
					<image :style='{"width":"120rpx","boxShadow":"0 0 8rpx rgba(0,0,0,.3)","borderRadius":"40rpx","textAlign":"right","height":"120rpx"}' class="avator" v-else src="../../static/gen/upload.png" mode="aspectFill"></image>
				</view>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0","borderStyle":"solid","height":"108rpx"}' class="cu-form-group select">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">卖家账号</view>
				<picker @change="maijiazhanghaoChange" :value="maijiazhanghaoIndex" :range="maijiazhanghaoOptions">
					<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' class="uni-input">{{ruleForm.maijiazhanghao?ruleForm.maijiazhanghao:"请选择卖家账号"}}</view>
				</picker>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0","borderStyle":"solid","height":"108rpx"}' class="cu-form-group select">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">卖家姓名</view>
				<picker @change="maijiaxingmingChange" :value="maijiaxingmingIndex" :range="maijiaxingmingOptions">
					<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' class="uni-input">{{ruleForm.maijiaxingming?ruleForm.maijiaxingming:"请选择卖家姓名"}}</view>
				</picker>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">规格</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.guige" v-model="ruleForm.guige" placeholder="规格"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">品牌</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.pinpai" v-model="ruleForm.pinpai" placeholder="品牌"></input>
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
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">出售单价</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.chushoudanjia" v-model="ruleForm.chushoudanjia" placeholder="出售单价"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">数量</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.shuliang" v-model="ruleForm.shuliang" placeholder="数量"></input>
			</view>
																																													
			<!-- 否 -->
 
			
			          				          				          				          				          				          				          				          				          				          				          				          				          				<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0 0 0 0","borderWidth":"0","borderStyle":"solid","height":"308rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">商品描述</view>
				<textarea :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"280rpx"}' v-model="ruleForm.shangpinmiaoshu" placeholder="商品描述"></textarea>
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
												shangpinbianhao: this.getUUID(),
																shangpinmingcheng: '',
																shangpinleibie: '',
																tupian: '',
																maijiazhanghao: '',
																maijiaxingming: '',
																guige: '',
																pinpai: '',
																xinjiuchengdu: '',
																yuanjia: '',
																chushoudanjia: '',
																shuliang: '',
																shangpinmiaoshu: '',
																thumbsupnum: '',
																crazilynum: '',
																clicknum: '',
												},
																												shangpinleibieOptions: [],
				shangpinleibieIndex: 0,
																								maijiazhanghaoOptions: [],
				maijiazhanghaoIndex: 0,
																maijiaxingmingOptions: [],
				maijiaxingmingIndex: 0,
																																																																																												// 登陆用户信息
				user: {},
                                ro:{
                                   shangpinbianhao : false,
                                   shangpinmingcheng : false,
                                   shangpinleibie : false,
                                   tupian : false,
                                   maijiazhanghao : false,
                                   maijiaxingming : false,
                                   guige : false,
                                   pinpai : false,
                                   xinjiuchengdu : false,
                                   yuanjia : false,
                                   chushoudanjia : false,
                                   shuliang : false,
                                   shangpinmiaoshu : false,
                                   thumbsupnum : false,
                                   crazilynum : false,
                                   clicknum : false,
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
																		// 下拉框
			res = await this.$api.option(`yonghu`,`yonghuming`,{});
			this.maijiazhanghaoOptions = res.data;
												// 下拉框
			res = await this.$api.option(`yonghu`,`xingming`,{});
			this.maijiaxingmingOptions = res.data;
																																																																					
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
				res = await this.$api.info(`shangpinxinxi`, this.ruleForm.id);
				this.ruleForm = res.data;
			}
			// 跨表
			if(options.cross){
				var obj = uni.getStorageSync('crossObj');
				for (var o in obj){
					if(o=='shangpinbianhao'){
					this.ruleForm.shangpinbianhao = obj[o];
					this.ro.shangpinbianhao = true;
					continue;
					}
					if(o=='shangpinmingcheng'){
					this.ruleForm.shangpinmingcheng = obj[o];
					this.ro.shangpinmingcheng = true;
					continue;
					}
					if(o=='shangpinleibie'){
					this.ruleForm.shangpinleibie = obj[o];
					this.ro.shangpinleibie = true;
					continue;
					}
					if(o=='tupian'){
					this.ruleForm.tupian = obj[o];
					this.ro.tupian = true;
					continue;
					}
					if(o=='maijiazhanghao'){
					this.ruleForm.maijiazhanghao = obj[o];
					this.ro.maijiazhanghao = true;
					continue;
					}
					if(o=='maijiaxingming'){
					this.ruleForm.maijiaxingming = obj[o];
					this.ro.maijiaxingming = true;
					continue;
					}
					if(o=='guige'){
					this.ruleForm.guige = obj[o];
					this.ro.guige = true;
					continue;
					}
					if(o=='pinpai'){
					this.ruleForm.pinpai = obj[o];
					this.ro.pinpai = true;
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
					if(o=='chushoudanjia'){
					this.ruleForm.chushoudanjia = obj[o];
					this.ro.chushoudanjia = true;
					continue;
					}
					if(o=='shuliang'){
					this.ruleForm.shuliang = obj[o];
					this.ro.shuliang = true;
					continue;
					}
					if(o=='shangpinmiaoshu'){
					this.ruleForm.shangpinmiaoshu = obj[o];
					this.ro.shangpinmiaoshu = true;
					continue;
					}
					if(o=='thumbsupnum'){
					this.ruleForm.thumbsupnum = obj[o];
					this.ro.thumbsupnum = true;
					continue;
					}
					if(o=='crazilynum'){
					this.ruleForm.crazilynum = obj[o];
					this.ro.crazilynum = true;
					continue;
					}
					if(o=='clicknum'){
					this.ruleForm.clicknum = obj[o];
					this.ro.clicknum = true;
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
																																																																																																						
			// 多级联动参数
																																																																																																						
																																																																																																			
																																																																																																			
																					// 下拉变化
			shangpinleibieChange(e) {
				this.shangpinleibieIndex = e.target.value
				this.ruleForm.shangpinleibie = this.shangpinleibieOptions[this.shangpinleibieIndex]
			},
																		// 下拉变化
			maijiazhanghaoChange(e) {
				this.maijiazhanghaoIndex = e.target.value
				this.ruleForm.maijiazhanghao = this.maijiazhanghaoOptions[this.maijiazhanghaoIndex]
			},
												// 下拉变化
			maijiaxingmingChange(e) {
				this.maijiaxingmingIndex = e.target.value
				this.ruleForm.maijiaxingming = this.maijiaxingmingOptions[this.maijiaxingmingIndex]
			},
																																																																		
																																				tupianTap() {
				let _this = this;
				this.$api.upload(function(res) {
					_this.ruleForm.tupian = _this.$base.url + 'upload/' + res.file;
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
																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																																				if(this.ruleForm.yuanjia&&(!this.$validate.isIntNumer(this.ruleForm.yuanjia))){
					this.$utils.msg(`原价应输入整数`);
					return
				}
																																												if(this.ruleForm.chushoudanjia&&(!this.$validate.isIntNumer(this.ruleForm.chushoudanjia))){
					this.$utils.msg(`出售单价应输入整数`);
					return
				}
																																												if(this.ruleForm.shuliang&&(!this.$validate.isIntNumer(this.ruleForm.shuliang))){
					this.$utils.msg(`数量应输入整数`);
					return
				}
																																																																																if(this.ruleForm.thumbsupnum&&(!this.$validate.isIntNumer(this.ruleForm.thumbsupnum))){
					this.$utils.msg(`赞应输入整数`);
					return
				}
																																												if(this.ruleForm.crazilynum&&(!this.$validate.isIntNumer(this.ruleForm.crazilynum))){
					this.$utils.msg(`踩应输入整数`);
					return
				}
																																												if(this.ruleForm.clicknum&&(!this.$validate.isIntNumer(this.ruleForm.clicknum))){
					this.$utils.msg(`点击次数应输入整数`);
					return
				}
																																				if(this.ruleForm.id){
					await this.$api.update(`shangpinxinxi`, this.ruleForm);
				}else{
					await this.$api.add(`shangpinxinxi`, this.ruleForm);
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
