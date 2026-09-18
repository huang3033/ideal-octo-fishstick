<template>
  <section class="login-side">
    <form class="card" @submit.prevent="handleLogin">
      <h1 class="welcome">欢迎回来</h1>
      <p class="subtitle">登录墨境，开启你的东方美学之旅</p>

      <!-- 账号 -->
      <div class="field">
        <label class="field-label" for="account">账号</label>
        <div class="input-row">
          <svg class="icon" viewBox="0 0 24 24" fill="none">
            <circle cx="12" cy="8" r="4" stroke="#8A857B" stroke-width="2" />
            <path d="M4 20c0-4 4-6 8-6s8 2 8 6" stroke="#8A857B" stroke-width="2" stroke-linecap="round" />
          </svg>
          <input id="account" v-model="form.account" type="text" placeholder="请输入手机号 / 邮箱" />
        </div>
      </div>

      <!-- 密码 -->
      <div class="field">
        <label class="field-label" for="password">密码</label>
        <div class="input-row">
          <svg class="icon" viewBox="0 0 24 24" fill="none">
            <rect x="5" y="11" width="14" height="9" rx="2" stroke="#8A857B" stroke-width="2" />
            <path d="M8 11V8a4 4 0 0 1 8 0v3" stroke="#8A857B" stroke-width="2" stroke-linecap="round" />
          </svg>
          <input id="password" v-model="form.password" type="password" placeholder="请输入密码" />
        </div>
      </div>

      <!-- 选项行 -->
      <div class="options">
        <label class="remember">
          <input type="checkbox" v-model="form.remember" />
          <span class="checkmark"></span>
          记住我
        </label>
        <a class="forgot" href="#" @click.prevent>忘记密码？</a>
      </div>

      <!-- 登录按钮 -->
      <button class="login-btn" type="submit">登 录</button>

      <!-- 分割线 -->
      <div class="divider"><span>其他登录方式</span></div>

      <!-- 社交登录 -->
      <div class="social">
        <button class="social-btn wechat" type="button" title="微信登录">
          <svg viewBox="0 0 24 24" fill="none">
            <path d="M8.5 4C5.5 4 3 6.2 3 9c0 1.7 1 3.2 2.6 4.2L5 16l2.7-1.4c.7.2 1.4.3 2.1.3h.4C9.8 13.9 9.5 12 11 10.7 10.2 6.7 9.4 4 8.5 4Z" fill="#2DC100" />
            <path d="M21 12.5c0-2.2-2-4-4.5-4S12 10.3 12 12.5 14 16.5 16.5 16.5c.5 0 1-.1 1.4-.2L20 18l-.5-1.8C20.3 15.2 21 14 21 12.5Z" fill="#2DC100" />
          </svg>
        </button>
        <button class="social-btn qq" type="button" title="QQ登录">
          <svg viewBox="0 0 24 24" fill="none">
            <path d="M12 3c3 0 4.5 2 4.5 4.5 0 1 .8 1.5 1.3 2.5.7 1.4.7 3 .2 4.5-.3.9-.2 1.8.3 2.5.4.5.2 1.3-.4 1.5-1 .3-1.7-.2-2.2-1-.4-.6-.6-1.4-.6-2.2 0 1.2-1.8 2-4 2s-4-.8-4-2c0 .8-.2 1.6-.6 2.2-.5.8-1.2 1.3-2.2 1-.6-.2-.8-1-.4-1.5.5-.7.6-1.6.3-2.5-.5-1.5-.5-3.1.2-4.5.5-1 1.3-1.5 1.3-2.5C7.5 5 9 3 12 3Z" fill="#12B7F5" />
          </svg>
        </button>
        <button class="social-btn more" type="button" title="更多登录">
          <svg viewBox="0 0 24 24" fill="none">
            <circle cx="12" cy="12" r="9" stroke="#E03D2B" stroke-width="2" />
            <path d="M12 8v8M8 12h8" stroke="#E03D2B" stroke-width="2" stroke-linecap="round" />
          </svg>
        </button>
      </div>

      <!-- 注册入口 -->
      <p class="footer">还没有账号？<a class="register" href="#" @click.prevent>立即注册</a></p>
    </form>
  </section>
</template>

<script setup>
import { reactive } from 'vue'

const form = reactive({
  account: '',
  password: '',
  remember: false
})

function handleLogin() {
  // 仅前端演示，无后端对接
  console.log('登录', { ...form })
  alert('这是前端演示，已打印登录信息到控制台。')
}
</script>

<style scoped>
.login-side {
  flex: 1 1 auto;
  height: 900px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--right-bg);
  transition: background 0.4s ease;
}

.card {
  width: 420px;
  padding: 44px 40px;
  display: flex;
  flex-direction: column;
  gap: 22px;
  background: var(--card-bg);
  border: 1px solid var(--card-border);
  border-radius: 20px;
  box-shadow: var(--card-shadow);
  transition: background 0.4s ease, border-color 0.4s ease;
}

.welcome {
  font-family: 'Noto Serif SC', serif;
  font-weight: 700;
  font-size: 34px;
  color: var(--ink);
}
.subtitle {
  margin-top: -14px;
  font-size: 14px;
  color: var(--ink-mute);
}

.field {
  display: flex;
  flex-direction: column;
  gap: 8px;
}
.field-label {
  font-size: 14px;
  font-weight: 500;
  color: var(--ink-soft);
}
.input-row {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 0 16px;
  height: 52px;
  background: var(--input-bg);
  border: 1px solid var(--input-border);
  border-radius: 10px;
  transition: border-color 0.2s ease, background 0.4s ease;
}
.input-row:focus-within {
  border-color: var(--cinnabar);
}
.icon {
  width: 20px;
  height: 20px;
  flex: 0 0 20px;
}
.input-row input {
  flex: 1 1 auto;
  border: none;
  outline: none;
  background: transparent;
  font-size: 15px;
  color: var(--ink);
  font-family: inherit;
}
.input-row input::placeholder {
  color: var(--placeholder);
}

.options {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 13px;
}
.remember {
  display: flex;
  align-items: center;
  gap: 8px;
  color: var(--ink-mute);
  cursor: pointer;
  user-select: none;
}
.remember input {
  position: absolute;
  opacity: 0;
  width: 0;
  height: 0;
}
.checkmark {
  width: 18px;
  height: 18px;
  border: 1px solid var(--input-border);
  border-radius: 5px;
  background: var(--input-bg);
  display: inline-block;
  position: relative;
}
.remember input:checked + .checkmark {
  background: var(--cinnabar);
  border-color: var(--cinnabar);
}
.remember input:checked + .checkmark::after {
  content: '';
  position: absolute;
  left: 5px;
  top: 1px;
  width: 5px;
  height: 10px;
  border: solid #fff;
  border-width: 0 2px 2px 0;
  transform: rotate(45deg);
}
.forgot {
  color: var(--cinnabar);
  font-weight: 500;
  text-decoration: none;
}
.forgot:hover {
  text-decoration: underline;
}

.login-btn {
  height: 52px;
  border: none;
  border-radius: 10px;
  background: var(--cinnabar);
  color: #fff;
  font-size: 17px;
  font-weight: 500;
  letter-spacing: 4px;
  cursor: pointer;
  box-shadow: var(--btn-shadow);
  transition: filter 0.2s ease;
}
.login-btn:hover {
  filter: brightness(1.05);
}

.divider {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 8px 0;
  color: var(--ink-mute);
  font-size: 12px;
}
.divider::before,
.divider::after {
  content: '';
  flex: 1 1 auto;
  height: 1px;
  background: var(--divider);
}

.social {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 18px;
  padding: 4px 0;
}
.social-btn {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  background: var(--card-bg);
  border: 1px solid var(--input-border);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.2s ease;
}
.social-btn svg {
  width: 26px;
  height: 26px;
}
.social-btn:hover {
  transform: translateY(-2px);
}

.footer {
  text-align: center;
  font-size: 13px;
  color: var(--ink-mute);
}
.register {
  color: var(--cinnabar);
  font-weight: 500;
  text-decoration: none;
}
.register:hover {
  text-decoration: underline;
}

@media (max-width: 960px) {
  .login-side {
    height: auto;
    padding: 48px 20px;
  }
  .card {
    width: 100%;
    max-width: 420px;
  }
}
</style>
