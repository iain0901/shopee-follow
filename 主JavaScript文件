// 獲取起始值、結束值和間隔時間
let start = parseInt(prompt("請輸入起始值:"));
let end = parseInt(prompt("請輸入結束值:"));
let interval = parseInt(prompt("請輸入間隔時間(秒):"));

// 檢查輸入是否有效
if (isNaN(start) || isNaN(end) || isNaN(interval) || start > end || interval <= 0) {
    alert("輸入無效,請確保起始值小於等於結束值,且間隔時間大於0。");
} else {
    // 初始化統計數據
    let stats = {
        totalClicks: 0,
        successfulClicks: 0,
        failedClicks: 0
    };

    // 創建統計顯示元素
    const statsDiv = document.createElement('div');
    statsDiv.style.position = 'fixed';
    statsDiv.style.top = '10px';
    statsDiv.style.right = '10px';
    statsDiv.style.backgroundColor = 'rgba(0, 0, 0, 0.7)';
    statsDiv.style.color = 'white';
    statsDiv.style.padding = '10px';
    statsDiv.style.borderRadius = '5px';
    document.body.appendChild(statsDiv);

    // 更新統計顯示
    function updateStats() {
        statsDiv.innerHTML = `
            總點擊次數: ${stats.totalClicks}<br>
            成功點擊: ${stats.successfulClicks}<br>
            失敗點擊: ${stats.failedClicks}<br>
            當前數值: ${current}
        `;
    }

    // 定義點擊函數
    function clickElement(number) {
        const selector = `div:nth-child(${number}) .USwYqi`;
        const element = document.querySelector(selector);
        stats.totalClicks++;
        if (element) {
            element.click();
            stats.successfulClicks++;
            console.log(`已點擊元素: ${selector}`);
        } else {
            stats.failedClicks++;
            console.log(`未找到元素: ${selector}`);
        }
        updateStats();
    }

    // 開始自動點擊過程
    let current = start;
    const intervalId = setInterval(() => {
        if (current <= end) {
            clickElement(current);
            current++;
        } else {
            clearInterval(intervalId);
            console.log("自動點擊過程已完成");
        }
    }, interval * 1000); // 將秒轉換為毫秒

    console.log("自動點擊過程已開始");
    updateStats();
}
