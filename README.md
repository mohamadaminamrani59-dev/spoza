[index.html.txt](https://github.com/user-attachments/files/23424908/index.html.txt)
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Spoza.ma - مساعد إنشاء المحتوى</title>
  <style>
    body {
      font-family: 'Tajawal', sans-serif;
      background-color: #f5f7fa;
      margin: 0;
      padding: 20px;
      color: #333;
    }
    .container {
      max-width: 800px;
      margin: auto;
      background: white;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.1);
    }
    h1, h2 {
      text-align: center;
      color: #2c3e50;
    }
    label {
      font-weight: bold;
      margin-top: 20px;
      display: block;
    }
    select, button {
      width: 100%;
      padding: 12px;
      font-size: 16px;
      border-radius: 8px;
      border: 1px solid #ddd;
      margin-top: 8px;
    }
    button {
      background: #e74c3c;
      color: white;
      border: none;
      cursor: pointer;
      font-weight: bold;
    }
    button:hover {
      background: #c0392b;
    }
    #result {
      margin-top: 30px;
      display: none;
    }
    .equipment, .video {
      margin-top: 20px;
      padding: 15px;
      background: #f8f9fa;
      border-radius: 8px;
      border-right: 4px solid #3498db;
    }
    iframe {
      width: 100%;
      height: 300px;
      border-radius: 8px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>مرحبًا بك في <span style="color:#e74c3c">Spoza.ma</span></h1>
    <p>اختر نوع المحتوى الذي ترغب في إنشائه، وسنساعدك بحسب الإمكانيات المتوفرة لديك.</p>

    <label for="contentType">ما نوع المحتوى الذي تريد إنشاءه؟</label>
    <select id="contentType">
      <option value="">اختر نوع المحتوى...</option>
      <option value="educational">فيديو تعليمي (شرح دروس، شروحات)</option>
      <option value="podcast">بودكاست (صوتي فقط)</option>
      <option value="vlog">فيديو يوميات (Vlog)</option>
      <option value="live">بث مباشر (لايف ستريمينغ)</option>
    </select>

    <button onclick="showRecommendation()">عرض التوصيات</button>

    <div id="result">
      <h2>التوصيات لك:</h2>
      <div class="equipment" id="equipment"></div>
      <div class="video">
        <h3>فيديو موصى به:</h3>
        <div id="videoEmbed"></div>
      </div>
    </div>
  </div>

  <script>
    const recommendations = {
      educational: {
        equipment: "إمكانيات موصى بها:<br>• كاميرا هاتف حديث (أو كاميرا ويب)<br>• مايك جيد (مثل: مايك طوق أو USB)<br>• إضاءة أمامية بسيطة (لمبة LED)<br>• برنامج مونتاج (مثل: CapCut أو DaVinci Resolve)",
        videoUrl: "https://www.youtube.com/embed/2wZv6X5VdK0" // فيديو مثال: "كيف تبدأ بصناعة المحتوى التعليمي"
      },
      podcast: {
        equipment: "إمكانيات موصى بها:<br>• مايك USB (مثل: Blue Yeti أو حتى سماعة جيدة)<br>• برنامج تسجيل (مثل: Audacity)<br>• مكان هادئ للتسجيل<br>• (اختياري) برنامج مونتاج صوتي بسيط",
        videoUrl: "https://www.youtube.com/embed/4QlGQ0iZ1hQ" // فيديو: "كيف تبدأ بودكاست من الصفر"
      },
      vlog: {
        equipment: "إمكانيات موصى بها:<br>• هاتف بجودة تصوير جيدة<br>• حامل ثلاثي (تريبود)<br>• مايك خارجي (مثل: Rode VideoMicro)<br>• تطبيق مونتاج (مثل: CapCut أو VN)",
        videoUrl: "https://www.youtube.com/embed/5Vh2nN3Fq6U" // فيديو: "نصائح لتصوير فيديوهات Vlog باحترافية"
      },
      live: {
        equipment: "إمكانيات موصى بها:<br>• إنترنت مستقر (5 Mbps فأكثر)<br>• كاميرا (أو هاتف)<br>• مايك خارجي<br>• منصة بث (مثل: YouTube Live أو Facebook Live)<br>• (اختياري) برامج مثل OBS Studio",
        videoUrl: "https://www.youtube.com/embed/9JgD7ZzL9dM" // فيديو: "كيف تبدأ بثًا مباشرًا على يوتيوب"
      }
    };

    function showRecommendation() {
      const type = document.getElementById("contentType").value;
      const resultDiv = document.getElementById("result");
      const equipmentDiv = document.getElementById("equipment");
      const videoDiv = document.getElementById("videoEmbed");

      if (!type) {
        alert("يرجى اختيار نوع المحتوى أولًا.");
        return;
      }

      const rec = recommendations[type];
      equipmentDiv.innerHTML = rec.equipment;
      videoDiv.innerHTML = `<iframe src="${rec.videoUrl}" frameborder="0" allowfullscreen></iframe>`;
      resultDiv.style.display = "block";
    }
  </script>
</body>
</html>
