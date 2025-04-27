<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>প্রতিষ্ঠান মনিটরিং সিস্টেম</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
        }
        .header {
            background-color: #4CAF50;
            color: white;
            padding: 20px;
            text-align: center;
        }
        .container {
            margin-top: 20px;
        }
        .card {
            margin-bottom: 20px;
        }
        .footer {
            text-align: center;
            padding: 10px;
            background-color: #333;
            color: white;
            position: absolute;
            width: 100%;
            bottom: 0;
        }
    </style>
</head>
<body>

    <!-- Header Section -->
    <div class="header">
        <h1>প্রতিষ্ঠান মনিটরিং সিস্টেম</h1>
    </div>

    <!-- Main Container -->
    <div class="container">
        <div class="row">
            <!-- Institution List Section -->
            <div class="col-md-6">
                <h3>প্রতিষ্ঠান তালিকা</h3>
                <div class="list-group">
                    <a href="#" class="list-group-item list-group-item-action">ধনুয়া উত্তর পাড়া</a>
                    <a href="#" class="list-group-item list-group-item-action">গাজীপুর পূর্ব পাড়া</a>
                    <a href="#" class="list-group-item list-group-item-action">কাচিনা</a>
                    <a href="#" class="list-group-item list-group-item-action">খন্দকার পাড়া</a>
                    <!-- Add More Institutions -->
                </div>
            </div>

            <!-- Monitoring Staff Section -->
            <div class="col-md-6">
                <h3>মনিটরিং খাদেম পোর্টাল</h3>
                <form id="login-form">
                    <div class="mb-3">
                        <label for="username" class="form-label">ইউজারনেম</label>
                        <input type="text" class="form-control" id="username" required>
                    </div>
                    <div class="mb-3">
                        <label for="password" class="form-label">পাসওয়ার্ড</label>
                        <input type="password" class="form-control" id="password" required>
                    </div>
                    <button type="submit" class="btn btn-primary">লগইন</button>
                </form>
            </div>
        </div>

        <div class="row">
            <!-- Transaction Record Section -->
            <div class="col-md-12">
                <h3>লেনদেন রেকর্ড</h3>
                <table class="table table-bordered">
                    <thead>
                        <tr>
                            <th>প্রতিষ্ঠান</th>
                            <th>লেনদেনের তারিখ</th>
                            <th>পরিমাণ</th>
                            <th>বর্ণনা</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>প্রতিষ্ঠান ১</td>
                            <td>০১-০৫-২০২৫</td>
                            <td>৳১০০০</td>
                            <td>বিক্রয় লেনদেন</td>
                        </tr>
                        <tr>
                            <td>প্রতিষ্ঠান ২</td>
                            <td>০২-০৫-২০২৫</td>
                            <td>৳৫০০</td>
                            <td>ব্যয়</td>
                        </tr>
                        <!-- Add More Transactions -->
                    </tbody>
                </table>
            </div>
        </div>
    </div>

    <!-- Footer Section -->
    <div class="footer">
        <p>&copy; 2025 প্রতিষ্ঠান মনিটরিং সিস্টেম | সকল অধিকার সংরক্ষিত</p>
    </div>

    <!-- JavaScript for form validation -->
    <script>
        document.getElementById('login-form').addEventListener('submit', function(e) {
            e.preventDefault();
            var username = document.getElementById('username').value;
            var password = document.getElementById('password').value;
            
            if (username === '' || password === '') {
                alert('অনুগ্রহ করে সব ফিল্ড পূরণ করুন');
            } else {
                alert('লগইন সফল');
            }
        });
    </script>

    <!-- Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
