<template>
	<vue-scroll class="forgot-password-page align-vertical">
		<div class="form-wrapper align-vertical-middle">
			<div class="form-box card-base card-shadow--extraLarge">
                <span class="logo">LOGO</span>
				
				<float-label class="styled">
					<input type="email" placeholder="E-mail" v-model="form.email">
				</float-label>

				<div class="flex text-center center pt-20 pb-10">			
					<el-button plain size="small" @click="login" class="send-btn tada animated">
						SEND RESET LINK
					</el-button>
				</div>
			</div>
		</div>
	</vue-scroll>
</template>

<script>
export default {
	name: 'ForgotPassword',
	data() {
		return {
			form: {
				email: '',
				password: '',
			}
		}
	},
	methods: {
		login() {
			this.$store.commit('setLogin')
			this.$router.push('dashboard')
		}
	}
}
</script>

<style lang="scss">
@import '../../../assets/scss/_variables';

.forgot-password-page {
	background: $text-color;
	margin-left: -30px;
	margin-right: -30px;

    .logo{
        font-style: normal;
        font-weight: 600;
        font-size: 24px;
        line-height: 20px;
        color: #000000;
        margin: 0px auto;
        margin-bottom: 70px;
        display: block;
        text-align: center;
        margin-top: 20px;
    }
	.form-wrapper {
		width: 100%;
	}
	
	.form-box {
		width: 100%;
		max-width: 340px;
		padding: 30px;
		box-sizing: border-box;
		margin: 20px auto;

		a {
			font-size: 14px;
			color: $text-color-accent;
			text-decoration: none;
			font-weight: 500;
		}

		.image-logo {
			width: 80px;
			margin: 0px auto;
			margin-bottom: 50px;
			display: block;
		}
        .vfl-label.vfl-label-on-input{
            display: none;
        }
        .vfl-has-label.styled .vfl-label.vfl-label-on-input + input{
            border-bottom: 1px solid #BABABA
        }

		.send-btn {
            padding: 12px 58px;
            border: 2px solid #5B5B5B;
            border-radius: 6px;
            span{
                font-weight: 600;
                font-size: 16px;
                line-height: 20px;
                color: #000000;
            }
		}
	}
}

@media (max-width: 768px) {
	.layout-container .container .view.forgot-password-page {
		margin-left: -5px;
		margin-right: -5px;
		max-width: calc(100% + 10px);
	}
}
</style>
