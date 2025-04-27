<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <title>ছক ফরম্যাট</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            width: 80%;
            background-color: white;
            padding: 20px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
        }

        h2 {
            text-align: center;
            font-size: 24px;
            color: #333;
        }

        p {
            text-align: center;
            font-size: 18px;
            color: #666;
        }

        table {
            border-collapse: collapse;
            width: 100%;
            direction: rtl; /* ডান থেকে বাম লেখা */
            margin-top: 20px;
        }

        th, td {
            border: 1px solid #ddd;
            padding: 12px;
            text-align: center;
        }

        th {
            background-color: #f4f4f4;
            font-size: 18px;
            color: #333;
        }

        td {
            font-size: 16px;
            color: #555;
        }

        tr:nth-child(even) {
            background-color: #f9f9f9;
        }

        tr:hover {
            background-color: #e9e9e9;
        }

        /* এখানে কলাম গুলোর সাইজ নির্ধারণ করা হলো */
        th:nth-child(1), td:nth-child(1) {
            width: 8%; /* প্রথম কলাম */
        }

        th:nth-child(2), td:nth-child(2) {
            width: 50%; /* দ্বিতীয় কলাম */
        }

        th:nth-child(3), td:nth-child(3) {
            width: 20%; /* তৃতীয় কলাম */
        }

        th:nth-child(4), td:nth-child(4) {
            width: 20%; /* চতুর্থ কলাম */
        }

        th:nth-child(5), td:nth-child(5) {
            width: 20%; /* পঞ্চম কলাম */
        }

        .footer {
            text-align: center;
            margin-top: 30px;
            font-size: 14px;
            color: #888;
        }

    </style>
</head>
<body>

<div class="container">
    <h2>আর্থিক বছরের প্রকল্পের ভৌত ও আর্থিক অগ্রগতির বিবরণী</h2>
    <p>প্রকল্পের নাম: __________________________</p>
    <p>অর্থ বছর: __________________________</p>

    <table>
        <thead>
            <tr>
                <th>ক্রমিক নং</th>
                <th>অফিস/বিভাগ</th>
                <th>কোড নং</th>
                <th>বসিবার স্থানের নাম</th>
                <th>ক্রমিক নং</th>
            </tr>
        </thead>
        <tbody>
            <!-- এখানে তোমার প্রয়োজন অনুযায়ী সারি (row) যোগ করা যাবে -->
            <tr>
                <td>১</td>
                <td>অফিস/বিভাগের নাম</td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td>২</td>
                <td>অফিস/বিভাগের নাম</td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <!-- আরো সারি যুক্ত করতে চাইলে একইভাবে কপি করে নিতে পারো -->
        </tbody>
    </table>

    <div class="footer">
        <p>© 2025 প্রকল্পের তথ্য</p>
    </div>
</div>

</body>
</html>
