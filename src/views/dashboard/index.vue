<template>
	<div ref="dashboardRef" class="dashboard-container column-page-wrap">
		<!-- 首页头部-卡片栏-1 -->
		<div class="lq-card">
			<div class="lq-card__content">
				<div class="flex-y-center justify-between">
					<div class="flex-y-center">
						<img src="../../assets/icons/user_new.svg" alt="user" style="width: 70px" />
						<div style="padding-left: 12px">
							<h3 class="text-18px font-semibold">早安，Lq, 今天又是充满活力的一天！</h3>
							<p class="leading-30px text-#999">今日多云转晴，20℃ - 25℃！</p>
						</div>
					</div>
					<div class="lq-space">
						<div class="lq-statistic whitespace-nowrap">
							<div class="lq-statistic__label">项目数</div>
							<div class="lq-statistic-value"><span class="lq-statistic-value__content">20</span></div>
						</div>
						<div class="lq-statistic whitespace-nowrap">
							<div class="lq-statistic__label">待办</div>
							<div class="lq-statistic-value"><span class="lq-statistic-value__content">6/20</span></div>
						</div>
						<div class="lq-statistic whitespace-nowrap">
							<div class="lq-statistic__label">消息</div>
							<div class="lq-statistic-value"><span class="lq-statistic-value__content">8</span></div>
						</div>
					</div>
				</div>
			</div>
		</div>
		<br />
		<!-- 首页头部-卡片栏-1 -->
		<div class="lq-card">
			<div class="lq-card__content">
				<div class="lq-grid">
					<div>
						<div class="grid-item linear-gradient">
							<h3>访问量</h3>
							<div class="flex justify-between pt-12px">
								<el-icon size="32"><Histogram /></el-icon>
								<span>1000</span>
							</div>
						</div>
					</div>
					<div>
						<div class="grid-item linear-gradient1">
							<h3>访问量</h3>
							<div class="flex justify-between pt-12px">
								<el-icon size="32"><PieChart /></el-icon>
								<span>1000</span>
							</div>
						</div>
					</div>
					<div>
						<div class="grid-item linear-gradient2">
							<h3>访问量</h3>
							<div class="flex justify-between pt-12px">
								<el-icon size="32"><Bell /></el-icon>
								<span>1000</span>
							</div>
						</div>
					</div>
					<div>
						<div class="grid-item linear-gradient3">
							<h3>访问量</h3>
							<div class="flex justify-between pt-12px">
								<el-icon size="32"><Monitor /></el-icon>
								<span>1000</span>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
.dashboard-container {
	overflow-y: auto;
	padding: 24px;
	background-color: rgb(246, 249, 248), 1;
	//background: var(--el-bg-color);
	//background: #f1f1fd;
	//background: var(--el-color-primary-light-9);
	position: relative;

	.card-panel__col {
		margin-bottom: 12px;
	}

	.chart-container {
		background: #ffffff;
	}
}

.lq-card {
	font-size: 14px;
	line-height: 1.6;
	display: flex;
	flex-direction: column;
	width: 100%;
	box-sizing: border-box;
	position: relative;
	border-radius: 8px;
	background-color: #fff;
	color: #333;
	word-break: break-word;
	box-shadow: 0 0 rgba(0, 0, 0, 0), 0 0 rgba(0, 0, 0, 0), 0 0 rgba(0, 0, 0, 0);
	transition: color 0.3s cubic-bezier(0.4, 0, 0.2, 1), background-color 0.3s cubic-bezier(0.4, 0, 0.2, 1),
		box-shadow 0.3s cubic-bezier(0.4, 0, 0.2, 1), border-color 0.3s cubic-bezier(0.4, 0, 0.2, 1);

	.lq-card__content {
		flex: 1;
		min-width: 0;
		padding: 20px 30px;
	}

	.lq-space {
		display: flex;
		flex-flow: row;
		justify-content: flex-start;
		gap: 24px;
	}

	.lq-statistic {
		.lq-statistic__label {
			font-weight: 400;
			transition: 0.3s color cubic-bezier(0.4, 0, 0.2, 1);
			font-size: 14px;
			color: rgb(118, 124, 130);
		}

		.lq-statistic-value {
			margin-top: 4px;
			font-weight: 600;

			.lq-statistic-value__content {
				transition: 0.3s color cubic-bezier(0.4, 0, 0.2, 1);
				font-size: 24px;
				color: rgb(51, 54, 57);
			}
		}
	}

	.lq-grid {
		width: 100%;
		display: grid;
		grid-template-columns: repeat(4, minmax(0px, 1fr));
		gap: 16px;
		div {
			grid-column: span 1 / span 1;

			.grid-item {
				padding: 16px;
				border-radius: 8px;
				height: 100px;
				color: #fff;
				h3 {
					font-size: 16px;
					font-weight: inherit;
				}
				span {
					font-size: 30px;
				}
			}
		}
	}
	.pt-12px {
		padding-top: 12px;
	}
	.linear-gradient {
		background-image: linear-gradient(to right bottom, rgb(236, 71, 134), rgb(185, 85, 164));
	}
	.linear-gradient1 {
		background-image: linear-gradient(to right bottom, rgb(134, 94, 192), rgb(81, 68, 180));
	}
	.linear-gradient2 {
		background-image: linear-gradient(to right bottom, rgb(86, 205, 243), rgb(113, 157, 227));
	}
	.linear-gradient3 {
		background-image: linear-gradient(to right bottom, rgb(252, 188, 37), rgb(246, 128, 87));
	}
}
</style>
