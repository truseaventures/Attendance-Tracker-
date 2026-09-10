<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>TruSea Ventures - Attendance</title>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
}

body {
    background: #f4f7fb;
    color: #172033;
}

/* HEADER */
.header {
    background: #ffffff;
    padding: 20px 35px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid #e5e7eb;
}

.logo-area h1 {
    font-size: 24px;
    color: #0b426b;
}

.logo-area p {
    color: #777;
    font-size: 13px;
    margin-top: 4px;
}

.date-time {
    text-align: right;
}

#currentDate {
    font-size: 14px;
    color: #666;
}

#currentTime {
    font-size: 20px;
    font-weight: bold;
    color: #0b426b;
    margin-top: 4px;
}

/* DASHBOARD */
.container {
    max-width: 1200px;
    margin: 30px auto;
    padding: 0 20px;
}

.dashboard-title {
    margin-bottom: 20px;
}

.dashboard-title h2 {
    font-size: 26px;
}

.dashboard-title p {
    color: #777;
    margin-top: 5px;
}

/* EMPLOYEE CARDS */
.employee-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 20px;
}

.employee-card {
    background: white;
    border-radius: 14px;
    padding: 25px;
    box-shadow: 0 5px 20px rgba(0,0,0,0.06);
    cursor: pointer;
    transition: 0.2s;
}

.employee-card:hover {
    transform: translateY(-3px);
}

.employee-top {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.employee-name {
    font-size: 21px;
    font-weight: bold;
}

.status {
    padding: 6px 12px;
    border-radius: 20px;
    font-size: 12px;
    font-weight: bold;
}

.present {
    background: #dcfce7;
    color: #15803d;
}

.absent {
    background: #fee2e2;
    color: #dc2626;
}

.pending {
    background: #fef3c7;
    color: #b45309;
}

.employee-info {
    margin-top: 20px;
    color: #555;
    line-height: 1.8;
}

/* DETAILS */
.details-section {
    display: none;
    margin-top: 30px;
}

.back-btn {
    border: none;
    background: #0b426b;
    color: white;
    padding: 10px 18px;
    border-radius: 8px;
    cursor: pointer;
    margin-bottom: 20px;
}

.profile-box {
    background: white;
    padding: 25px;
    border-radius: 14px;
    box-shadow: 0 5px 20px rgba(0,0,0,0.06);
}

.profile-box h2 {
    color: #0b426b;
    margin-bottom: 20px;
}

/* ACTION BUTTONS */
.action-buttons {
    display: flex;
    gap: 15px;
    margin-top: 20px;
}

button {
    border: none;
    cursor: pointer;
}

.login-btn {
    background: #16a34a;
    color: white;
    padding: 12px 25px;
    border-radius: 8px;
    font-weight: bold;
}

.logout-btn {
    background: #dc2626;
    color: white;
    padding: 12px 25px;
    border-radius: 8px;
    font-weight: bold;
}

button:disabled {
    background: #aaa;
    cursor: not-allowed;
}

.notice-box {
    margin-top: 15px;
    padding: 12px;
    background: #fee2e2;
    color: #b91c1c;
    border-radius: 8px;
    font-size: 13px;
    display: none;
}

/* CALENDAR */
.calendar-section {
    margin-top: 30px;
    background: white;
    padding: 25px;
    border-radius: 14px;
}

.calendar-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}

.calendar-header button {
    background: #0b426b;
    color: white;
    padding: 8px 15px;
    border-radius: 6px;
}

.calendar {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    gap: 8px;
}

.day-name {
    text-align: center;
    font-weight: bold;
    color: #777;
    padding: 10px 0;
}

.day {
    min-height: 70px;
    border-radius: 8px;
    padding: 8px;
    text-align: center;
    background: #f8fafc;
    border: 1px solid #e5e7eb;
    cursor: default;
}

.day.present-day {
    background: #dcfce7;
    border: 1px solid #22c55e;
    color: #15803d;
    cursor: pointer;
}

.day.absent-day {
    background: #fee2e2;
    border: 1px solid #ef4444;
    color: #dc2626;
    cursor: pointer;
}

.day-number {
    font-weight: bold;
    font-size: 15px;
}

.day-status {
    font-size: 11px;
    margin-top: 7px;
}

/* REPORT */
.report-section {
    margin-top: 30px;
    background: white;
    padding: 25px;
    border-radius: 14px;
    overflow-x: auto;
}

.report-summary {
    display: flex;
    gap: 20px;
    margin: 15px 0;
    flex-wrap: wrap;
    font-size: 13px;
    color: #555;
}

.report-summary b {
    color: #0b426b;
}

.report-table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 15px;
}

.report-table th,
.report-table td {
    padding: 12px;
    border-bottom: 1px solid #eee;
    text-align: left;
}

.report-table th {
    background: #f8fafc;
}

/* LOCATION */
.location-box {
    margin-top: 15px;
    padding: 12px;
    background: #f8fafc;
    border-radius: 8px;
    font-size: 13px;
}

/* MOBILE */
@media(max-width:600px) {

    .header {
        padding: 15px;
    }

    .logo-area h1 {
        font-size: 19px;
    }

    .date-time {
        display: none;
    }

    .container {
        margin-top: 20px;
    }

    .action-buttons {
        flex-direction: column;
    }

    .calendar {
        gap: 4px;
    }

    .day {
        min-height: 55px;
        padding: 5px;
    }
}
</style>
</head>

<body>

<header class="header">

    <div class="logo-area">
        <h1>TRUSEA VENTURES</h1>
        <p>Employee Attendance Management</p>
    </div>

    <div class="date-time">
        <div id="currentDate"></div>
        <div id="currentTime"></div>
    </div>

</header>


<div class="container">

    <!-- DASHBOARD -->

    <div id="dashboard">

        <div class="dashboard-title">
            <h2>Employee Dashboard</h2>
            <p>Select an employee to view attendance</p>
        </div>

        <div class="employee-grid">

            <div class="employee-card" onclick="openEmployee('Karthi')">

                <div class="employee-top">
                    <div class="employee-name">Karthi</div>
                    <div id="karthiStatus" class="status pending">
                        Pending
                    </div>
                </div>

                <div class="employee-info">
                    <div>Login: <span id="karthiLogin">--</span></div>
                    <div>Logout: <span id="karthiLogout">--</span></div>
                </div>

            </div>


            <div class="employee-card" onclick="openEmployee('Santhosh')">

                <div class="employee-top">
                    <div class="employee-name">Santhosh</div>
                    <div id="santhoshStatus" class="status pending">
                        Pending
                    </div>
                </div>

                <div class="employee-info">
                    <div>Login: <span id="santhoshLogin">--</span></div>
                    <div>Logout: <span id="santhoshLogout">--</span></div>
                </div>

            </div>

        </div>

    </div>


    <!-- EMPLOYEE DETAILS -->

    <div id="detailsSection" class="details-section">

        <button class="back-btn" onclick="backToDashboard()">
            ← Back to Dashboard
        </button>

        <div class="profile-box">

            <h2 id="selectedEmployee">
                Employee
            </h2>

            <p>
                Today's Status:
                <strong id="todayStatus">Pending</strong>
            </p>

            <div class="action-buttons">

                <button
                    id="loginButton"
                    class="login-btn"
                    onclick="loginEmployee()">
                    LOGIN
                </button>

                <button
                    id="logoutButton"
                    class="logout-btn"
                    onclick="logoutEmployee()"
                    disabled>
                    LOGOUT
                </button>

            </div>

            <div id="noticeBox" class="notice-box"></div>

            <div class="location-box">

                <strong>Current Location:</strong>

                <div id="locationText">
                    Location will be detected during login.
                </div>

            </div>

        </div>


        <!-- CALENDAR -->

        <div class="calendar-section">

            <div class="calendar-header">

                <button onclick="previousMonth()">‹</button>

                <h3 id="calendarMonth"></h3>

                <button onclick="nextMonth()">›</button>

            </div>

            <div class="calendar" id="calendar"></div>

        </div>


        <!-- REPORT -->

        <div class="report-section">

            <h3>Attendance Report</h3>

            <div class="report-summary">
                <div>Working Days: <b id="repWorking">0</b></div>
                <div>Present: <b id="repPresent">0</b></div>
                <div>Absent: <b id="repAbsent">0</b></div>
                <div>Attendance %: <b id="repPct">0%</b></div>
            </div>

            <table class="report-table">

                <thead>

                    <tr>
                        <th>Date</th>
                        <th>Status</th>
                        <th>Login</th>
                        <th>Logout</th>
                        <th>Location</th>
                    </tr>

                </thead>

                <tbody id="reportBody">

                </tbody>

            </table>

        </div>

    </div>

</div>


<script>

/* =========================
   CONFIGURATION
========================= */

const GOOGLE_SCRIPT_URL =
"https://script.google.com/macros/s/AKfycbzN81dHc08YfGiPtsXV0HmW0NlcA4V4wXVvPzstCRRPCE4PHVzWxHWtKf0GMoNv69Gl8g/exec";

const LOGIN_DEADLINE_HOUR = 10;

let selectedEmployee = "";
let selectedDate = new Date();
let refreshTimer = null;


/* =========================
   CLOCK
========================= */

function updateClock() {

    const now = new Date();

    document.getElementById("currentDate").innerText =
        now.toLocaleDateString("en-IN", {
            weekday: "long",
            day: "2-digit",
            month: "long",
            year: "numeric"
        });

    document.getElementById("currentTime").innerText =
        now.toLocaleTimeString("en-IN");

}

setInterval(updateClock, 1000);
updateClock();


/* =========================
   API HELPERS
========================= */

function apiGet(params) {

    const url = new URL(GOOGLE_SCRIPT_URL);

    Object.keys(params).forEach(k =>
        url.searchParams.set(k, params[k])
    );

    return fetch(url.toString())
        .then(res => res.json());
}

function apiPost(payload) {

    // text/plain avoids a CORS preflight, which Apps Script
    // web apps do not support — this lets us actually read
    // the JSON response (success / message) back.
    return fetch(GOOGLE_SCRIPT_URL, {

        method: "POST",

        headers: {
            "Content-Type": "text/plain;charset=utf-8"
        },

        body: JSON.stringify(payload)

    }).then(res => res.json());

}


/* =========================
   DASHBOARD
========================= */

function loadDashboard() {

    apiGet({ action: "today" })
        .then(resp => {

            if (!resp.success) return;

            resp.data.forEach(rec => {

                const key = rec.name.toLowerCase();

                const statusEl =
                    document.getElementById(key + "Status");

                const loginEl =
                    document.getElementById(key + "Login");

                const logoutEl =
                    document.getElementById(key + "Logout");

                if (!statusEl) return;

                setStatusPill(statusEl, rec.status);

                loginEl.innerText = rec.loginTime || "--";
                logoutEl.innerText = rec.logoutTime || "--";

            });

        })
        .catch(err => console.log("Dashboard load error", err));

}

function setStatusPill(el, status) {

    el.classList.remove("present", "absent", "pending");

    if (status === "Present") {
        el.classList.add("present");
        el.innerText = "Present";
    } else if (status === "Absent") {
        el.classList.add("absent");
        el.innerText = "Absent";
    } else {
        el.classList.add("pending");
        el.innerText = "Pending";
    }

}

loadDashboard();
setInterval(loadDashboard, 45000);


/* =========================
   EMPLOYEE
========================= */

function openEmployee(name) {

    selectedEmployee = name;
    selectedDate = new Date();

    document.getElementById("dashboard")
        .style.display = "none";

    document.getElementById("detailsSection")
        .style.display = "block";

    document.getElementById("selectedEmployee")
        .innerText = name;

    document.getElementById("noticeBox").style.display = "none";

    loadTodayStatus();
    generateCalendar();

    if (refreshTimer) clearInterval(refreshTimer);
    refreshTimer = setInterval(loadTodayStatus, 45000);

}


function backToDashboard() {

    document.getElementById("dashboard")
        .style.display = "block";

    document.getElementById("detailsSection")
        .style.display = "none";

    if (refreshTimer) clearInterval(refreshTimer);

    loadDashboard();

}


function loadTodayStatus() {

    apiGet({ action: "employee", name: selectedEmployee })
        .then(resp => {

            if (!resp.success) return;

            const d = resp.data;

            document.getElementById("todayStatus")
                .innerText = d.status;

            const loginBtn = document.getElementById("loginButton");
            const logoutBtn = document.getElementById("logoutButton");
            const notice = document.getElementById("noticeBox");

            if (d.loginLocation || d.logoutLocation) {

                let loc = d.loginLocation || "";

                if (d.logoutLocation) {
                    loc += (loc ? " → Logout: " : "Logout: ") + d.logoutLocation;
                }

                document.getElementById("locationText").innerText = loc;

            }

            if (d.status === "Present" && !d.logoutTime) {

                loginBtn.disabled = true;
                logoutBtn.disabled = false;
                notice.style.display = "none";

            } else if (d.status === "Present" && d.logoutTime) {

                loginBtn.disabled = true;
                logoutBtn.disabled = true;
                notice.style.display = "none";

            } else if (d.status === "Absent") {

                loginBtn.disabled = true;
                logoutBtn.disabled = true;
                notice.innerText = "Login time is closed. You are marked Absent for today.";
                notice.style.display = "block";

            } else {

                loginBtn.disabled = isPastDeadline();
                logoutBtn.disabled = true;
                notice.style.display = "none";

            }

        });

}

function isPastDeadline() {

    // Convenience check only — the Apps Script backend re-checks
    // this using its own server clock, so it cannot be bypassed
    // by changing the device's time.
    const now = new Date();
    return now.getHours() >= LOGIN_DEADLINE_HOUR;

}


/* =========================
   LOGIN
========================= */

function loginEmployee() {

    if (!navigator.geolocation) {

        alert("Location access is required for attendance.");
        return;

    }

    const loginBtn = document.getElementById("loginButton");
    loginBtn.disabled = true;
    loginBtn.innerText = "Getting location...";

    navigator.geolocation.getCurrentPosition(

        function(position) {

            const latitude = position.coords.latitude;
            const longitude = position.coords.longitude;
            const location = latitude.toFixed(5) + ", " + longitude.toFixed(5);

            document.getElementById("locationText").innerText = location;

            loginBtn.innerText = "Logging in...";

            apiPost({
                action: "login",
                employee: selectedEmployee,
                latitude: latitude,
                longitude: longitude,
                location: location
            })
            .then(resp => {

                if (resp.success) {
                    alert(resp.message || "Login recorded successfully.");
                } else {
                    alert(resp.message);
                }

            })
            .catch(() => alert("Could not reach the server. Please try again."))
            .finally(() => {
                loginBtn.innerText = "LOGIN";
                loadTodayStatus();
                loadDashboard();
                generateCalendar();
            });

        },

        function() {

            loginBtn.disabled = false;
            loginBtn.innerText = "LOGIN";
            alert("Please allow location permission to login.");

        },

        { enableHighAccuracy: true, timeout: 10000 }

    );

}


/* =========================
   LOGOUT
========================= */

function logoutEmployee() {

    if (!navigator.geolocation) {

        alert("Location access is required for attendance.");
        return;

    }

    const logoutBtn = document.getElementById("logoutButton");
    logoutBtn.disabled = true;
    logoutBtn.innerText = "Getting location...";

    navigator.geolocation.getCurrentPosition(

        function(position) {

            const latitude = position.coords.latitude;
            const longitude = position.coords.longitude;
            const location = latitude.toFixed(5) + ", " + longitude.toFixed(5);

            logoutBtn.innerText = "Logging out...";

            apiPost({
                action: "logout",
                employee: selectedEmployee,
                latitude: latitude,
                longitude: longitude,
                location: location
            })
            .then(resp => {

                if (resp.success) {
                    alert(resp.message || "Logout recorded successfully.");
                } else {
                    alert(resp.message);
                    logoutBtn.disabled = false;
                }

            })
            .catch(() => {
                alert("Could not reach the server. Please try again.");
                logoutBtn.disabled = false;
            })
            .finally(() => {
                logoutBtn.innerText = "LOGOUT";
                loadTodayStatus();
                loadDashboard();
                generateCalendar();
            });

        },

        function() {

            logoutBtn.disabled = false;
            logoutBtn.innerText = "LOGOUT";
            alert("Please allow location permission to logout.");

        },

        { enableHighAccuracy: true, timeout: 10000 }

    );

}


/* =========================
   CALENDAR + REPORT
========================= */

function generateCalendar() {

    const calendar = document.getElementById("calendar");
    calendar.innerHTML = "";

    const year = selectedDate.getFullYear();
    const month = selectedDate.getMonth();

    const monthName = selectedDate.toLocaleDateString("en-IN", {
        month: "long",
        year: "numeric"
    });

    document.getElementById("calendarMonth").innerText = monthName;

    const dayNames = ["Sun","Mon","Tue","Wed","Thu","Fri","Sat"];

    dayNames.forEach(day => {
        const el = document.createElement("div");
        el.className = "day-name";
        el.innerText = day;
        calendar.appendChild(el);
    });

    const firstDay = new Date(year, month, 1).getDay();
    const totalDays = new Date(year, month + 1, 0).getDate();

    for (let i = 0; i < firstDay; i++) {
        calendar.appendChild(document.createElement("div"));
    }

    const monthKey = year + "-" + String(month + 1).padStart(2, "0");

    apiGet({ action: "calendar", name: selectedEmployee, month: monthKey })
        .then(resp => {

            const records = {};

            if (resp.success) {
                resp.data.forEach(rec => {
                    const day = parseInt(String(rec.date).split("/")[0], 10);
                    records[day] = rec;
                });
            }

            for (let day = 1; day <= totalDays; day++) {

                const rec = records[day];
                const cell = document.createElement("div");
                cell.className = "day";

                let statusText = "-";

                if (rec) {
                    if (rec.status === "Present") {
                        cell.classList.add("present-day");
                        statusText = "Present";
                    } else if (rec.status === "Absent") {
                        cell.classList.add("absent-day");
                        statusText = "Absent";
                    }
                    cell.onclick = () => showDayDetails(rec);
                }

                cell.innerHTML = `
                    <div class="day-number">${day}</div>
                    <div class="day-status">${statusText}</div>
                `;

                calendar.appendChild(cell);

            }

            renderReportTable(resp.success ? resp.data : []);

        });

    apiGet({ action: "monthly", name: selectedEmployee, month: monthKey })
        .then(resp => {

            if (!resp.success) return;

            document.getElementById("repWorking").innerText = resp.data.workingDays;
            document.getElementById("repPresent").innerText = resp.data.present;
            document.getElementById("repAbsent").innerText = resp.data.absent;
            document.getElementById("repPct").innerText = resp.data.percentage + "%";

        });

}

function showDayDetails(rec) {

    alert(
        rec.date + " — " + rec.status +
        "\nLogin: " + (rec.loginTime || "--") +
        "\nLogout: " + (rec.logoutTime || "--") +
        "\nLogin Location: " + (rec.loginLocation || "--") +
        "\nLogout Location: " + (rec.logoutLocation || "--")
    );

}

function renderReportTable(data) {

    const tbody = document.getElementById("reportBody");
    tbody.innerHTML = "";

    if (!data.length) {
        tbody.innerHTML = `<tr><td colspan="5" style="text-align:center;color:#777;padding:16px;">No records for this month</td></tr>`;
        return;
    }

    data.forEach(row => {

        const tr = document.createElement("tr");

        tr.innerHTML = `
            <td>${row.date || "--"}</td>
            <td>
                <span class="status ${row.status === "Present" ? "present" : "absent"}">
                    ${row.status || "--"}
                </span>
            </td>
            <td>${row.loginTime || "--"}</td>
            <td>${row.logoutTime || "--"}</td>
            <td>${row.loginLocation || "--"}</td>
        `;

        tbody.appendChild(tr);

    });

}


/* =========================
   MONTH NAVIGATION
========================= */

function previousMonth() {
    selectedDate.setMonth(selectedDate.getMonth() - 1);
    generateCalendar();
}

function nextMonth() {
    selectedDate.setMonth(selectedDate.getMonth() + 1);
    generateCalendar();
}

</script>

</body>
</html>
