<head>
    <meta charset="UTF-8">
    <title>wqc倒计时</title>
    <style>
        .div {
            position: relative;
            width: 1000px;
            margin: 150px auto;
            font-size: 300%;
            text-align: center;
        }

        .div-day {
            font-size: 100px;
        }
        .div-time {
            font-size: 50px;
        }
    </style>
</head>
<body>
<div class="div">
    <h3>王庆晨式专业证书考试倒计时</h3>
    <h5>距离下次考试还有</h5>
    <div class="div-day">
    </div>
    <div class="div-time">
    </div>
</div>
<script>
    let second;
    let day;

    function rkCountDown() {
        const nowTime = +new Date();
        const rkTime = +new Date('2022-5-28 9:00:00');
        let times = rkTime - nowTime;
        day = parseInt(times / 1000 / 60 / 60 / 24);
        day = day < 10 ? '0' + day : day;
        let hour = parseInt(times / 1000 / 60 / 60 % 24);
        hour = hour < 10 ? '0' + hour : hour;
        let minute = parseInt(times / 1000 / 60 % 60);
        minute = minute < 10 ? '0' + minute : minute;
        second = parseInt(times / 1000 % 60);
        second = second < 10 ? '0' + second : second;
        let ms = parseInt(times % 1000);
        ms = ms < 100 ? ms < 10 ? '00' + ms : '0' + ms : ms;
        return hour + ':' + minute + ':' + second + ' . ' + ms;
    }

    let ts = 1;
    window.setInterval(function () {
        const divDay = document.querySelector('.div-day');
        divDay.innerHTML = day + '天';
        const divTime = document.querySelector('.div-time');
        divTime.innerHTML = rkCountDown();
        const h5 = document.querySelector('h5');
        switch (second % 10) {
            case 0:
                h5.style.color = '#FF0000';
                break;
            case 1:
                h5.style.color = '#FF00FF';
                break;
            case 2:
                h5.style.color = '#FF7F00';
                break;
            case 3:
                h5.style.color = '#D98719';
                break;
            case 4:
                h5.style.color = '#B5A642';
                break;
            case 5:
                h5.style.color = '#238E23';
                break;
            case 6:
                h5.style.color = '#4A766E';
                break;
            case 7:
                h5.style.color = '#7093DB';
                break;
            case 8:
                h5.style.color = '#4D4Dff';
                break;
            case 9:
                h5.style.color = '#CC3299';
                break;
        }
    }, 1);
</script>
</body>
