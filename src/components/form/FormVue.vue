<template>
	<div>
		<div>
			<!-- 多行文本输入并显示 -->
			<br>
			<span>Multiline message is:</span>
			<p style="white-space: pre-line;">{{ message }}</p>
			<br>
			<textarea v-model="message" placeholder="add multiple lines"></textarea>
			<br>
		</div>
		<dir>
			<!-- 单选框 -->
			<!-- <input type="checkbox" id="checkbox" v-model="checked">
			<label for="checkbox">{{ checked }}</label> -->
		</dir>
		<div>
			<!-- 复选框，实现全部选中和取消全部选中 -->
			<br>
			<input type="checkbox" id="checkbox" v-model="checked" @click="changeAllChecked()">
			<label for="checkbox" v-if="checked === false">全选</label>
			<label for="checkbox" v-else>取消</label>

			<input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
			<label for="jack">Jack</label>
			<input type="checkbox" id="john" value="John" v-model="checkedNames">
			<label for="john">John</label>
			<input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
			<label for="mike">Mike</label>
			<br>
			<br>
			<span>Checked names: {{ checkedNames }}</span>
		</div>
		<div>
			<!-- 单选按钮 -->
			<br>
			<input type="radio" id="one" value="One" v-model="picked">
			<label for="one">One</label>
			<br>
			<input type="radio" id="two" value="Two" v-model="picked">
			<label for="two">Two</label>
		 	<br>
			<span>Picked: {{ picked }}</span>
		</div>
		<div>
			<!-- 下拉选择框 -->
			<br>
			<select v-model="selected">
				<option disabled value="">请选择</option>
			    <option>A</option>
			    <option>B</option>
			    <option>C</option>
			</select>
			<span>Selected: {{ selected }}</span>
		</div>
	</div>
	
</template>

<script>
export default {
	name: 'FromVue',
	data() {
		return {
			message: '',
			checked: false,
			picked: '',
			checkedNames: [],
			checked_1: true,
			checkedArr: ["Jack", "John", "Mike"],
			selected: []
		}
	},
	methods: {
		changeAllChecked: function() {
			console.log(this.checked)
			if (!this.checked) {
				this.checkedNames = this.checkedArr
			} else {
				this.checkedNames = []
			}
		}
	},
	watch: {
		checkedNames: function() {
			if (this.checkedNames.length != this.checkedArr.length) {
				this.checked = false
			} else {
				this.checked = true
			}
		}
	}
}
</script>

<style scoped>
	
</style>