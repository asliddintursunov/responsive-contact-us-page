<template>
    <div id="container">
        <div id="inputs">
            <form>
                <div class="left">
                    <div>
                        <pre>name</pre>
                        <input type="text" id="name" v-model.trim.lazy="userInfo.userName" placeholder="first name"
                            class="name userInputs">
                        <input type="text" id="name" v-model.lazy="userInfo.userSecondName" placeholder="second name"
                            class="second-name userInputs">
                    </div>

                    <div>
                        <pre>phone number</pre>
                        <input type="number" id="number" placeholder="ex: 99 890 123 45 67" v-model.number="userInfo.userNumber"
                            class="number userInputs">
                    </div>

                    <div>
                        <pre>address</pre>
                        <input type="text" id="address" placeholder="ex: Washington, USA" v-model.lazy="userInfo.userAddress"
                            class="address userInputs">
                    </div>
                </div>
                <div class="right">
                    <div>
                        <pre>skills</pre>
                        <select id="skill" multiple v-model="userInfo.userSkills" class="multiple-select userInputs">
                            <option value="HTML">HTML</option>
                            <option value="CSS">CSS</option>
                            <option value="SCSS/SASS">Scss/Sass</option>
                            <option value="JavaScript">JavaScriot</option>
                            <option value="TypeScript">TypeScript</option>
                            <option value="Angular JS">Angular JS</option>
                            <option value="Vue JS">Vue JS</option>
                            <option value="React JS">React JS</option>
                            <option value="Git/GitHub">Git/GitHub</option>
                        </select>
                    </div>

                    <div>
                        <pre>level</pre>
                        <select id="level" v-model="userInfo.userLevel" class="level userInputs">
                            <option value="">Select level</option>
                            <option value="junior">Junior</option>
                            <option value="strong-junior">Strong Junior</option>
                            <option value="middle">Middle</option>
                            <option value="strong-middle">Strong Middle</option>
                            <option value="senior">Senior</option>
                            <option value="principal">Principal</option>
                        </select>
                    </div>

                    <div>
                        <pre>age</pre>
                        <input type="radio" id="16-19" value="16-19" v-model="userInfo.userAge" class="age">
                        <label for="16-19">16-19</label>

                        <input type="radio" id="20-24" value="20-24" v-model="userInfo.userAge" class="age">
                        <label for="20-24">20-24</label>

                        <input type="radio" id="25-31" value="25-31" v-model="userInfo.userAge" class="age">
                        <label for="25-31">25-31</label>
                    </div>

                    <div>
                        <pre>working place</pre>
                        <input type="checkbox" id="remotework" true-value="Yes" false-value="No"
                            v-model="userInfo.remoteWorking" class="working-remotely">
                        <label for="remotework">working remotely</label>
                    </div>
                </div>
                <div class="middle_bottom">
                    <div>
                        <pre>summary</pre>
                        <textarea v-model="userInfo.userSummary" cols="35" rows="5" placeholder="Write your summary here"
                            class="summary userInputs" />
                    </div>

                    <button type="submit" @click.prevent="submitMethod">Submit</button>
                </div>
            </form>
        </div>
        <div id="outputs">
            <div class="left_top_out">

                <div>
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="w-6 h-6">
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="M15.75 6a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0zM4.501 20.118a7.5 7.5 0 0114.998 0A17.933 17.933 0 0112 21.75c-2.676 0-5.216-.584-7.499-1.632z" />
                    </svg>
                    <h3>{{ userInfo.userName }} {{ userInfo.userSecondName }}</h3>
                </div>
                <div>
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="w-6 h-6">
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 002.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 01-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 00-1.091-.852H4.5A2.25 2.25 0 002.25 4.5v2.25z" />
                    </svg>
                    <div>
                        <h3>{{ userInfo.userNumber }}</h3>
                    </div>
                </div>
                <div>
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="w-6 h-6">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M15 10.5a3 3 0 11-6 0 3 3 0 016 0z" />
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1115 0z" />
                    </svg>
                    <h3>{{ userInfo.userAddress }}</h3>
                </div>
            </div>
            <div class="right_top_out">

                <div>
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="w-6 h-6">
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="M15.666 3.888A2.25 2.25 0 0013.5 2.25h-3c-1.03 0-1.9.693-2.166 1.638m7.332 0c.055.194.084.4.084.612v0a.75.75 0 01-.75.75H9a.75.75 0 01-.75-.75v0c0-.212.03-.418.084-.612m7.332 0c.646.049 1.288.11 1.927.184 1.1.128 1.907 1.077 1.907 2.185V19.5a2.25 2.25 0 01-2.25 2.25H6.75A2.25 2.25 0 014.5 19.5V6.257c0-1.108.806-2.057 1.907-2.185a48.208 48.208 0 011.927-.184" />
                    </svg>
                    <h3>{{ userInfo.userSkills.join(', ') }}</h3>
                </div>
                <div>
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="w-6 h-6">
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="M3 13.125C3 12.504 3.504 12 4.125 12h2.25c.621 0 1.125.504 1.125 1.125v6.75C7.5 20.496 6.996 21 6.375 21h-2.25A1.125 1.125 0 013 19.875v-6.75zM9.75 8.625c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125v11.25c0 .621-.504 1.125-1.125 1.125h-2.25a1.125 1.125 0 01-1.125-1.125V8.625zM16.5 4.125c0-.621.504-1.125 1.125-1.125h2.25C20.496 3 21 3.504 21 4.125v15.75c0 .621-.504 1.125-1.125 1.125h-2.25a1.125 1.125 0 01-1.125-1.125V4.125z" />
                    </svg>
                    <h3>{{ userInfo.userLevel }}</h3>
                </div>
            </div>
            <div class="left_bottom_out">
                <div>
                    <h3>Age: {{ userInfo.userAge }}</h3>
                </div>
                <div>
                    <h3>Working remotely: {{ userInfo.remoteWorking }}</h3>
                </div>
            </div>
            <div class="right_bottom_out">

                <div>
                    <p>
                        <strong>Summary:</strong>
                        {{ userInfo.userSummary }}
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts">
export default {
    data() {
        return {
            userInfo: {
                userName: '',
                userSecondName: '',
                userNumber: '',
                userAddress: '',
                userSkills: [],
                userLevel: '',
                userAge: '',
                remoteWorking: 'No',
                userSummary: '',
            }
        }
    },
    methods: {
        submitMethod() {
            console.log(this.userInfo);
        },
    }
}
</script>
<style scoped>
.left,
.right,
.middle_bottom {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-around;
    flex: 1;
}

#outputs div {
    display: flex;
    align-items: center;
    justify-content: flex-start;
}

.left_top_out>div,
.right_top_out>div,
.left_bottom_out>div,
.right_bottom_out>div {
    display: flex;
    flex-direction: column;
    align-items: center;
    flex: 1;
}
</style>
    