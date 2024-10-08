<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Open Front Camera</title>
</head>
<body>
    <h1>Click to Open Front Camera</h1>
    <video id="video" autoplay></video>

    <script>
        const constraints = {
            video: {
                facingMode: "user" // Mở camera trước
            }
        };

        navigator.mediaDevices.getUserMedia(constraints)
            .then((stream) => {
                const video = document.getElementById('video');
                video.srcObject = stream;
            })
            .catch((err) => {
                console.error('Lỗi khi truy cập camera: ', err);
            });
    </script>
</body>
</html>