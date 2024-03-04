let timer;
let startTime;
let elapsedTime = 0;
let isRunning = false;

function startTimer() {
    if (!isRunning) {
        startTime = Date.now() - elapsedTime;
        timer = setInterval(updateDisplay, 10);
        isRunning = true;
    }
}

function stopTimer() {
    if (isRunning) {
        clearInterval(timer);
        isRunning = false;
    }
}

function resetTimer() {
    clearInterval(timer);
    isRunning = false;
    elapsedTime = 0;
    updateDisplay();
}

function updateDisplay() {
    const currentTime = Date.now();
    elapsedTime = currentTime - startTime;
    document.querySelector('.display').innerText = formatTime(elapsedTime);
}

function formatTime(time) {
    const totalMilliseconds = time;
    const totalSeconds = Math.floor(totalMilliseconds / 1000);
    const hours = Math.floor(totalSeconds / 3600);
    const minutes = Math.floor((totalSeconds % 3600) / 60);
    const seconds = totalSeconds % 60;
    const milliseconds = totalMilliseconds % 1000;

    return (
        (hours > 0 ? hours + ':' : '') +
        String(minutes).padStart(2, '0') +
        ':' +
        String(seconds).padStart(2, '0') +
        '.' +
        String(milliseconds).padStart(3, '0')
    );
}

document.getElementById('startBtn').addEventListener('click', startTimer);
document.getElementById('stopBtn').addEventListener('click', stopTimer);
document.getElementById('resetBtn').addEventListener('click', resetTimer);

// Add touch event listeners
document.getElementById('startBtn').addEventListener('touchstart', startTimer);
document.getElementById('stopBtn').addEventListener('touchstart', stopTimer);
document.getElementById('resetBtn').addEventListener('touchstart', resetTimer);


// Initial display
updateDisplay();

