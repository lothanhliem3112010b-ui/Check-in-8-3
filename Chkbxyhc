<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EMC 8/3 Check-in</title>
    <style>
        body { margin: 0; display: flex; flex-direction: column; align-items: center; background: #fff0f3; font-family: sans-serif; }
        h1 { color: #ff4d6d; margin: 20px 0; }
        .camera-wrapper { width: 320px; height: 320px; border: 8px solid #ff85a2; border-radius: 15px; overflow: hidden; background: #ccc; }
        video { width: 100%; height: 100%; object-fit: cover; }
        .btn-box { margin-top: 20px; display: flex; gap: 10px; }
        button { padding: 10px 20px; border: none; border-radius: 20px; background: #ff4d6d; color: white; font-weight: bold; cursor: pointer; }
    </style>
</head>
<body>

    <h1>EMC 8/3</h1>
    <div class="camera-wrapper">
        <video id="video" autoplay playsinline></video>
    </div>
    <div class="btn-box">
        <button onclick="startCamera('user')">Cam Trước</button>
        <button onclick="startCamera('environment')">Cam Sau</button>
    </div>

    <script>
        const video = document.getElementById('video');

        async function startCamera(mode) {
            try {
                // Dừng stream cũ nếu có
                if (window.currentStream) {
                    window.currentStream.getTracks().forEach(track => track.stop());
                }
                
                const stream = await navigator.mediaDevices.getUserMedia({
                    video: { facingMode: mode },
                    audio: false
                });
                
                window.currentStream = stream;
                video.srcObject = stream;
            } catch (err) {
                alert("Lỗi truy cập Camera: " + err.message + ". Vui lòng cấp quyền trong cài đặt trình duyệt.");
            }
        }

        // Tự động bật cam trước khi tải trang
        startCamera('user');
    </script>
</body>
</html>
