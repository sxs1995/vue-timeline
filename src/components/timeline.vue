<template>
  <div class="timelines">
    <div class="timeline">
      <div class="timeline_l" v-for="(item,index) in 12" :key="index">
        <div
          class="item"
          :class="(playing==(index) && playing !=1)||playing==(index+1)?playing !=12?'active':'':''"
        ></div>
        <div class="dot" :class="playing==(index+1)?'dotactive':''"></div>
        <div
          class="item"
          :class="playing == 1?'':(playing==(index+1)||playing==(index+2) && playing!=12)?'active':''"
        ></div>
      </div>
    </div>
    <div class="timeline_time">
      <ul>
        <li>2019-01</li>
        <li>2019-02</li>
        <li>2019-03</li>
        <li>2019-04</li>
        <li>2019-05</li>
        <li>2019-06</li>
        <li>2019-07</li>
        <li>2019-08</li>
        <li>2019-09</li>
        <li>2019-10</li>
        <li>2019-11</li>
        <li>2019-12</li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  name:'timeline',
	data() {
		return {
			playing: 1,
		};
	},
};
</script>
<style lang="scss">
/*时间轴*/
ul,
li {
	margin: 0;
	padding: 0;
}
.timelines {
	.timeline {
		display: flex;
		height: 35px;

		.timeline_l {
			flex: 1;
			display: flex;
			justify-content: center;
			align-items: center;

			.dot {
				border: 2px solid #41d5ce;
				width: 12px;
				height: 12px;
				background: #1d706c;
				border-radius: 50%;
				margin: auto;
				transition: all ease 1s;
			}

			.item {
				flex: 1;
				height: 2px; // width: 20px;
				background: #41d5ce;
				transition: all ease 2s;
			}

			.active {
				background: #ff9000 !important;
			}

			.dotactive {
				width: 18px;
				height: 18px;
				background-color: #ff5a00;
				border: solid 2px #ff9000;
			}

			.timeline_t {
				flex: 1;
			}
		}
	}

	.timeline_time {
		ul {
			display: flex;

			li {
				list-style: none;
				flex: 1;
				text-align: center;
				color: #000;
				font-size: 12px;
			}
		}
	}
}
</style>
