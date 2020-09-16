<template>
	<vue-scroll class="login-page align-vertical">
		<div class="form-wrapper align-vertical-middle">
			<div class="form-box card-base card-shadow--extraLarge">
				<span class="logo">LOGO</span>

                <float-label class="styled">
					<input type="email" v-model="form.email" placeholder="E-mail">
				</float-label>
				<float-label class="styled">
					<input :type="type" v-model="form.password" placeholder="Password">
                    <svg v-if="type=='password'" @click="type = 'text'" class="close-eye" width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M9.9 4.23999C10.5883 4.07887 11.2931 3.99833 12 3.99999C19 3.99999 23 12 23 12C22.393 13.1356 21.6691 14.2047 20.84 15.19M14.12 14.12C13.8454 14.4147 13.5141 14.6511 13.1462 14.8151C12.7782 14.9791 12.3809 15.0673 11.9781 15.0744C11.5753 15.0815 11.1752 15.0074 10.8016 14.8565C10.4281 14.7056 10.0887 14.481 9.80385 14.1961C9.51897 13.9113 9.29439 13.5719 9.14351 13.1984C8.99262 12.8248 8.91853 12.4247 8.92563 12.0219C8.93274 11.6191 9.02091 11.2218 9.18488 10.8538C9.34884 10.4858 9.58525 10.1546 9.88 9.87999M17.94 17.94C16.2306 19.243 14.1491 19.9649 12 20C5 20 1 12 1 12C2.24389 9.68189 3.96914 7.6566 6.06 6.05999L17.94 17.94Z" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        <path d="M1 1L23 23" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                    </svg>
                    <svg v-if="type=='text'" @click="type = 'password'" class="close-eye" width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M1 12C1 12 5 4 12 4C19 4 23 12 23 12C23 12 19 20 12 20C5 20 1 12 1 12Z" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        <path d="M12 15C13.6569 15 15 13.6569 15 12C15 10.3431 13.6569 9 12 9C10.3431 9 9 10.3431 9 12C9 13.6569 10.3431 15 12 15Z" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                    </svg>

                </float-label>
				
				<div class="flex">
					<div class="box grow"><checkbox title="Remember Me" /></div>
					<div class="box grow text-right"><router-link to="/forgot-password">Forgot Password?</router-link></div>
				</div>

				<div class="flex text-center center pt-30 pb-10">			
					<el-button plain size="small" @click="login" class="login-btn tada animated">
						LOGIN
					</el-button>
				</div>

				<div class="text-divider mv-10">or</div>

				<div class="flex column center pt-10 pb-10">			
					<el-button plain size="small" @click="login" class="social-btn google">
						Log in with Google
					</el-button>
					<el-button plain size="small" @click="login" class="social-btn facebook">
						Log in with Facebook
					</el-button>
				</div>

				<div class="text-center signin-box pt-20">
					<span>Don't have an account? <router-link to="/register">Sign in</router-link></span>
				</div>
			</div>
		</div>
	</vue-scroll>
</template>

<script>
    import checkbox from "../../../components/main_components/checkbox";


export default {
	name: 'Login',
    components:{
        checkbox
    },
	data() {
		return {
		    type:'password',
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

.login-page {
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
    .vfl-has-label.styled{
        position: relative;
    }
    .vfl-has-label.styled .vfl-label + input {
        width: 88%;
        padding-right: 37px;
    }
    .vfl-label.vfl-label-on-input{
        display: none;
    }
    .vfl-has-label.styled .vfl-label.vfl-label-on-input + input{
        border-bottom: 1px solid #BABABA
    }

    .close-eye{
        position: absolute;
        right: 4px;
        top: 2px;
        cursor: pointer;
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
			margin-bottom: 30px;
			display: block;
		}

        .login-btn{
            padding: 12px 58px;
            width: 164px;
            height: 44px;
            border: 2px solid #5B5B5B;
            border-radius: 6px!important;
            font-style: normal;
            font-weight: 500;
            font-size: 16px;
            line-height: 20px;
            span{
                color: #000000!important;
            }
        }

		.social-btn {
			width: 188px;

			&.google {
				margin-bottom: 10px;
				background-color: #d73d32;
				color: white;
                border-radius: 2px;
                padding: 8px 42px;
                width: 188px;
                height: 36px;

				&:hover {
					border-color: #d73d32;
				}
			}
			&.facebook {
				background-color: #3f5c9a;
				color: white;
                border-radius: 2px;
                padding: 8px 42px;
                width: 188px;
                height: 36px;

				&:hover {
					border-color: #3f5c9a;
				}
			}
		}

		.signin-box {
			font-size: 14px;
            color: #000000;
            span{
                display: inline-block;
                border-bottom: 1px solid #000000;
            }
		}
	}
}

@media (max-width: 768px) {
	.layout-container .container .view.login-page {
		margin-left: -5px;
		margin-right: -5px;
		max-width: calc(100% + 10px);
	}
}
</style>
