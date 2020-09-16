<template>
	<vue-scroll class="register-page align-vertical">
		<div class="form-wrapper align-vertical-middle">
			<div class="form-box card-base card-shadow--extraLarge">
<!--				<img class="image-logo" src="@/assets/images/logo.svg" alt="logo"/>-->
                <span class="logo">LOGO</span>
				
				<float-label class="styled">
					<input type="text" placeholder="Name" v-model="form.name">
				</float-label>
				<float-label class="styled">
					<input type="email" placeholder="E-mail" v-model="form.email">
				</float-label>
				<float-label class="styled">
					<input type="password" placeholder="Password" v-model="form.password">
				</float-label>
				<float-label class="styled">
					<input type="password" placeholder="Password (confirm)" v-model="form.confirm_password">
				</float-label>
				
				<div class="flex">
					<div class="box grow"><el-checkbox>I read and accept terms</el-checkbox></div>
				</div>

				<div class="flex text-center center pt-30 pb-20">			
					<el-button plain size="small" @click="login" class="signin-btn tada animated">
						SIGN IN
					</el-button>
				</div>

				<div class="text-center login-box pt-10">
					Already have an account? <router-link to="/login">Login</router-link>
				</div>
			</div>
		</div>
	</vue-scroll>
</template>

<script>
export default {
	name: 'Register',
	data() {
		return {
			form: {
				name: '',
				email: '',
				password: '',
				confirm_password: '',
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

.register-page {
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
    .vfl-label.vfl-label-on-input{
        display: none;
    }
    .vfl-has-label.styled .vfl-label.vfl-label-on-input + input{
        border-bottom: 1px solid #BABABA
    }
    .el-checkbox__input.is-checked + .el-checkbox__label{
        text-decoration: underline;
        color: #000000;
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

		.signin-btn {
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

		.login-box {
			font-size: 14px;
		}
	}
}

@media (max-width: 768px) {
	.layout-container .container .view.register-page {
		margin-left: -5px;
		margin-right: -5px;
		max-width: calc(100% + 10px);
	}
}
</style>
