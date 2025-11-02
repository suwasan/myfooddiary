<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ไดอารี่ร้านอาหารและตัวติดตาม GPS</title>
    <!-- โหลด Tailwind CSS เพื่อความง่ายในการออกแบบ responsive -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* กำหนดฟอนต์ Inter และการปรับแต่งพื้นฐานสำหรับ UI ไทย */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f4f7f6;
        }
        /* Style สำหรับ Loading/Message Box */
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }
        .message-box {
            background-color: white;
            padding: 24px;
            border-radius: 12px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            max-width: 90%;
            text-align: center;
        }
    </style>
</head>
<body>

    <!-- Message/Loading Overlay (ใช้แทน alert() ) -->
    <div id="overlay" class="overlay">
        <div class="message-box" id="messageBox">
            <div id="messageText" class="text-gray-700 text-lg font-medium mb-3">กำลังโหลด...</div>
            <button id="closeMessage" class="px-4 py-2 bg-indigo-600 text-white rounded-lg hover:bg-indigo-700 transition duration-150 hidden">ตกลง</button>
        </div>
    </div>

    <div class="container mx-auto p-4 max-w-2xl">
        <h1 class="text-3xl font-bold text-center text-indigo-700 mb-6 mt-4">
            ไดอารี่ร้านอาหารส่วนตัว
        </h1>
        <p class="text-center text-sm text-gray-500 mb-6">
            <span class="font-semibold" id="authStatus"></span>
        </p>

        <!-- ส่วนแสดงตำแหน่งปัจจุบัน -->
        <div class="bg-white p-4 rounded-xl shadow-lg mb-6">
            <h2 class="text-xl font-semibold text-gray-800 mb-3 flex items-center">
                <svg class="w-6 h-6 mr-2 text-indigo-500" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.828 0l-4.243-4.243a8 8 0 1111.314 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
                ตำแหน่งปัจจุบัน (GPS)
            </h2>
            <div id="currentLocation" class="text-base text-gray-600">
                <p>Latitude: <span id="currentLat">รอการดึงข้อมูล...</span></p>
                <p>Longitude: <span id="currentLng">รอการดึงข้อมูล...</span></p>
            </div>
            <button onclick="getGeolocation()" class="mt-3 w-full bg-green-500 text-white py-2 rounded-lg hover:bg-green-600 transition duration-150 shadow-md">
                <span id="locationButtonText">ดึงตำแหน่งอีกครั้ง</span>
            </button>
        </div>

        <!-- ส่วนเพิ่มร้านอาหารใหม่ -->
        <div class="bg-white p-4 rounded-xl shadow-lg mb-6">
            <h2 class="text-xl font-semibold text-gray-800 mb-3 flex items-center">
                <svg class="w-6 h-6 mr-2 text-indigo-500" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v3m0 0v3m0-3h3m-3 0H9m12 0a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                เพิ่มร้านอาหารใหม่
            </h2>
            <input type="text" id="restaurantName" placeholder="ชื่อร้านอาหาร" class="w-full p-3 mb-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-500">
            <div class="flex space-x-2 mb-3">
                 <input type="number" id="newLat" placeholder="Latitude (อัตโนมัติ)" class="w-1/2 p-3 border border-gray-300 rounded-lg focus:outline-none" readonly>
                 <input type="number" id="newLng" placeholder="Longitude (อัตโนมัติ)" class="w-1/2 p-3 border border-gray-300 rounded-lg focus:outline-none" readonly>
            </div>
            <button onclick="useCurrentLocationForNew()" class="w-full bg-yellow-500 text-gray-800 py-2 rounded-lg hover:bg-yellow-600 transition duration-150 shadow-md mb-3">
                ใช้ตำแหน่งปัจจุบัน
            </button>
            <button onclick="addRestaurant()" class="w-full bg-indigo-600 text-white py-2 rounded-lg hover:bg-indigo-700 transition duration-150 shadow-md">
                บันทึกร้านอาหาร
            </button>
        </div>

        <!-- ส่วนรายการร้านอาหารที่บันทึกไว้ -->
        <div class="bg-white p-4 rounded-xl shadow-lg">
            <h2 class="text-xl font-semibold text-gray-800 mb-3 flex items-center">
                <svg class="w-6 h-6 mr-2 text-indigo-500" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2m-6 0h.01m-6 0h.01"></path></svg>
                ร้านอาหารที่ฉันบันทึกไว้ (<span id="restaurantCount">0</span>)
            </h2>
            <div id="restaurantList" class="space-y-3">
                <!-- รายการร้านอาหารจะถูกเพิ่มเข้ามาที่นี่ด้วย JavaScript -->
                <p id="loadingIndicator" class="text-center text-gray-500">กำลังโหลดรายการร้านอาหาร...</p>
                <p id="noRestaurants" class="text-center text-gray-500 hidden">ไม่มีร้านอาหารที่บันทึกไว้</p>
            </div>
        </div>

        <!-- Modal สำหรับเพิ่ม/ดูรายละเอียดอาหาร -->
        <div id="foodModal" class="overlay">
            <div class="message-box w-full max-w-lg">
                <h3 class="text-2xl font-bold text-indigo-700 mb-4" id="modalRestaurantName">รายละเอียดร้านอาหาร</h3>

                <h4 class="text-lg font-semibold text-gray-700 mb-2">บันทึกรายการอาหาร:</h4>
                <div class="mb-4">
                    <input type="text" id="foodItemName" placeholder="ชื่อรายการอาหาร" class="w-full p-2 mb-2 border border-gray-300 rounded-lg">
                    <textarea id="foodMemo" placeholder="บันทึกย่อ (เช่น 'เผ็ดเกินไป' หรือ 'อร่อยมาก')" class="w-full p-2 mb-2 border border-gray-300 rounded-lg"></textarea>
                    <div class="flex justify-around space-x-2">
                        <button onclick="addFoodItem('like')" class="w-full py-2 bg-pink-500 text-white rounded-lg hover:bg-pink-600 transition duration-150 flex items-center justify-center">
                             <svg class="w-5 h-5 mr-1" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z" clip-rule="evenodd"></path></svg>
                             ชอบ (อร่อย)
                        </button>
                        <button onclick="addFoodItem('dislike')" class="w-full py-2 bg-red-500 text-white rounded-lg hover:bg-red-600 transition duration-150 flex items-center justify-center">
                            <svg class="w-5 h-5 mr-1" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M10 2a5 5 0 00-5 5v2h10V7a5 5 0 00-5-5z"></path><path d="M4 12c0-.621.5-1.121 1.121-1.121h9.758C15.5 10.879 16 11.379 16 12v3c0 .621-.5 1.121-1.121 1.121H5.121C4.5 16.121 4 15.621 4 15v-3z"></path></svg>
                            ไม่ชอบ (ไม่อร่อย)
                        </button>
                    </div>
                </div>

                <h4 class="text-lg font-semibold text-gray-700 mb-2 mt-4">รายการที่บันทึก:</h4>
                <div id="foodListDetails" class="max-h-60 overflow-y-auto p-2 border border-gray-200 rounded-lg bg-gray-50 space-y-2 text-left">
                    <p class="text-sm text-gray-500">ยังไม่มีรายการอาหารที่บันทึก</p>
                </div>

                <button onclick="closeFoodModal()" class="mt-6 px-6 py-2 bg-gray-500 text-white rounded-lg hover:bg-gray-600 transition duration-150">
                    ปิด
                </button>
            </div>
        </div>

    </div>

    <!-- Firebase SDKs -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInAnonymously, signInWithCustomToken, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, doc, addDoc, setDoc, onSnapshot, collection, query, updateDoc, arrayUnion } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

        // Global variables for Firebase configuration (provided by the Canvas environment)
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'default-app-id';
        const firebaseConfig = typeof __firebase_config !== 'undefined' ? JSON.parse(__firebase_config) : {};
        const initialAuthToken = typeof __initial_auth_token !== 'undefined' ? __initial_auth_token : null;

        let db;
        let auth;
        let userId = null;
        let currentRestaurantDocId = null;
        let currentRestaurants = {}; // เก็บข้อมูลร้านอาหารที่ดึงมาจาก Firestore

        // --- Utility Functions ---

        /** แสดงข้อความในกล่องข้อความ (ใช้แทน alert()) */
        window.showMessage = (text, isError = false) => {
            document.getElementById('messageText').textContent = text;
            const closeButton = document.getElementById('closeMessage');
            closeButton.onclick = closeMessage;
            closeButton.classList.remove('hidden');
            if (isError) {
                 document.getElementById('messageBox').classList.add('border-4', 'border-red-500');
            } else {
                 document.getElementById('messageBox').classList.remove('border-4', 'border-red-500');
            }
            document.getElementById('overlay').style.display = 'flex';
        }

        /** ปิดกล่องข้อความ */
        window.closeMessage = () => {
            document.getElementById('overlay').style.display = 'none';
        }

        /** แสดง Loading Indicator */
        window.showLoading = (text = 'กำลังดำเนินการ...') => {
            document.getElementById('messageText').textContent = text;
            document.getElementById('closeMessage').classList.add('hidden');
            document.getElementById('overlay').style.display = 'flex';
        }

        /** ซ่อน Loading Indicator */
        window.hideLoading = () => {
             document.getElementById('overlay').style.display = 'none';
        }

        // --- Geolocation Functions ---

        let currentLat = null;
        let currentLng = null;

        /** ดึงตำแหน่ง GPS ปัจจุบัน */
        window.getGeolocation = () => {
            const buttonText = document.getElementById('locationButtonText');
            buttonText.textContent = 'กำลังดึงตำแหน่ง...';

            if (!navigator.geolocation) {
                showMessage('เบราว์เซอร์นี้ไม่รองรับ Geolocation', true);
                buttonText.textContent = 'ดึงตำแหน่งอีกครั้ง';
                return;
            }

            navigator.geolocation.getCurrentPosition(
                (position) => {
                    currentLat = position.coords.latitude;
                    currentLng = position.coords.longitude;
                    document.getElementById('currentLat').textContent = currentLat.toFixed(6);
                    document.getElementById('currentLng').textContent = currentLng.toFixed(6);
                    buttonText.textContent = 'ตำแหน่งถูกดึงแล้ว';
                },
                (error) => {
                    let errorMessage;
                    switch (error.code) {
                        case error.PERMISSION_DENIED:
                            errorMessage = "คุณปฏิเสธการเข้าถึงตำแหน่ง โปรดอนุญาตในการตั้งค่าเบราว์เซอร์";
                            break;
                        case error.POSITION_UNAVAILABLE:
                            errorMessage = "ข้อมูลตำแหน่งไม่พร้อมใช้งาน";
                            break;
                        case error.TIMEOUT:
                            errorMessage = "หมดเวลาในการดึงข้อมูลตำแหน่ง";
                            break;
                        default:
                            errorMessage = "เกิดข้อผิดพลาดในการดึงตำแหน่ง: " + error.message;
                            break;
                    }
                    showMessage(errorMessage, true);
                    document.getElementById('currentLat').textContent = 'ข้อผิดพลาด';
                    document.getElementById('currentLng').textContent = 'ข้อผิดพลาด';
                    buttonText.textContent = 'ดึงตำแหน่งอีกครั้ง';
                },
                { enableHighAccuracy: true, timeout: 5000, maximumAge: 0 }
            );
        }

        /** ใช้ตำแหน่งปัจจุบันสำหรับฟอร์มเพิ่มร้านอาหาร */
        window.useCurrentLocationForNew = () => {
            if (currentLat === null || currentLng === null) {
                showMessage('กรุณาดึงตำแหน่ง GPS ปัจจุบันก่อน', true);
                getGeolocation(); // ลองดึงอีกครั้ง
                return;
            }
            document.getElementById('newLat').value = currentLat;
            document.getElementById('newLng').value = currentLng;
        }

        // --- Firestore Data Operations (Restaurant) ---

        /** สร้าง path สำหรับ Collection ร้านอาหารส่วนตัว */
        const getRestaurantCollectionPath = () => {
            if (!userId) {
                throw new Error("User not authenticated.");
            }
            // Path ส่วนตัวสำหรับผู้ใช้คนเดียว: /artifacts/{appId}/users/{userId}/restaurants
            return `artifacts/${appId}/users/${userId}/restaurants`;
        }

        /** เพิ่มร้านอาหารใหม่ */
        window.addRestaurant = async () => {
            if (!userId) {
                showMessage('กรุณารอการตรวจสอบสิทธิ์ผู้ใช้ก่อน', true);
                return;
            }

            const name = document.getElementById('restaurantName').value.trim();
            const lat = parseFloat(document.getElementById('newLat').value);
            const lng = parseFloat(document.getElementById('newLng').value);

            if (!name) {
                showMessage('กรุณากรอกชื่อร้านอาหาร', true);
                return;
            }
            if (isNaN(lat) || isNaN(lng)) {
                showMessage('กรุณาเลือกหรือกรอกตำแหน่ง Latitude และ Longitude ที่ถูกต้อง', true);
                return;
            }

            showLoading('กำลังบันทึกร้านอาหาร...');

            try {
                const restaurantData = {
                    name: name,
                    lat: lat,
                    lng: lng,
                    foods: [] // เริ่มต้นด้วยรายการอาหารว่าง
                };

                const docRef = await addDoc(collection(db, getRestaurantCollectionPath()), restaurantData);

                // เคลียร์ฟอร์ม
                document.getElementById('restaurantName').value = '';
                document.getElementById('newLat').value = '';
                document.getElementById('newLng').value = '';

                hideLoading();
                showMessage(`บันทึกร้านอาหาร "${name}" เรียบร้อย!`);

            } catch (e) {
                console.error("Error adding document: ", e);
                hideLoading();
                showMessage("เกิดข้อผิดพลาดในการบันทึกข้อมูล: " + e.message, true);
            }
        }

        /** เปิด Modal เพื่อดู/เพิ่มรายการอาหาร */
        window.openFoodModal = (docId) => {
            const restaurant = currentRestaurants[docId];
            if (!restaurant) {
                showMessage('ไม่พบข้อมูลร้านอาหาร', true);
                return;
            }

            currentRestaurantDocId = docId;
            document.getElementById('modalRestaurantName').textContent = restaurant.name;
            document.getElementById('foodItemName').value = '';
            document.getElementById('foodMemo').value = '';

            renderFoodItems(restaurant.foods);

            document.getElementById('foodModal').style.display = 'flex';
        }

        /** ปิด Modal รายการอาหาร */
        window.closeFoodModal = () => {
            document.getElementById('foodModal').style.display = 'none';
            currentRestaurantDocId = null;
        }

        /** เพิ่มรายการอาหาร (Like/Dislike) */
        window.addFoodItem = async (status) => { // status: 'like' หรือ 'dislike'
            if (!currentRestaurantDocId) return;

            const itemName = document.getElementById('foodItemName').value.trim();
            const memo = document.getElementById('foodMemo').value.trim();

            if (!itemName) {
                showMessage('กรุณากรอกชื่อรายการอาหาร', true);
                return;
            }

            showLoading('กำลังบันทึกรายการอาหาร...');

            try {
                const docRef = doc(db, getRestaurantCollectionPath(), currentRestaurantDocId);

                const newFoodItem = {
                    item: itemName,
                    status: status,
                    memo: memo || (status === 'like' ? 'อร่อยมาก' : 'ไม่ถูกปาก'),
                    timestamp: new Date().toISOString()
                };

                // ใช้ arrayUnion เพื่อเพิ่ม object เข้าไปใน array 'foods'
                await updateDoc(docRef, {
                    foods: arrayUnion(newFoodItem)
                });

                document.getElementById('foodItemName').value = '';
                document.getElementById('foodMemo').value = '';

                hideLoading();
                showMessage(`บันทึก "${itemName}" เป็นรายการ${status === 'like' ? 'โปรด' : 'ไม่ชอบ'}เรียบร้อย!`);

            } catch (e) {
                console.error("Error updating document: ", e);
                hideLoading();
                showMessage("เกิดข้อผิดพลาดในการบันทึกรายการอาหาร: " + e.message, true);
            }
        }

        /** แสดงรายการอาหารใน Modal */
        const renderFoodItems = (foods) => {
            const listContainer = document.getElementById('foodListDetails');
            listContainer.innerHTML = '';

            if (foods.length === 0) {
                listContainer.innerHTML = '<p class="text-sm text-gray-500">ยังไม่มีรายการอาหารที่บันทึก</p>';
                return;
            }

            // เรียงลำดับจากล่าสุด
            foods.sort((a, b) => new Date(b.timestamp) - new Date(a.timestamp));

            foods.forEach(food => {
                const isLike = food.status === 'like';
                const statusIcon = isLike ? '❤️' : '🤢';
                const statusColor = isLike ? 'bg-pink-100 text-pink-700' : 'bg-red-100 text-red-700';

                const foodElement = `
                    <div class="p-3 border rounded-lg flex items-start space-x-3 ${isLike ? 'border-pink-300' : 'border-red-300'}">
                        <div class="text-xl pt-1">${statusIcon}</div>
                        <div class="flex-grow">
                            <p class="font-medium text-gray-800">${food.item}</p>
                            <p class="text-xs ${statusColor} inline-block px-2 py-0.5 rounded-full">${isLike ? 'ชอบมาก' : 'ไม่ชอบ'}</p>
                            <p class="text-sm text-gray-600 mt-1">${food.memo}</p>
                        </div>
                    </div>
                `;
                listContainer.innerHTML += foodElement;
            });
        }

        /** Render รายการร้านอาหารหลัก */
        const renderRestaurants = (restaurants) => {
            const listContainer = document.getElementById('restaurantList');
            const countDisplay = document.getElementById('restaurantCount');
            const noRestaurants = document.getElementById('noRestaurants');
            listContainer.innerHTML = '';
            currentRestaurants = {}; // รีเซ็ต

            if (restaurants.length === 0) {
                noRestaurants.classList.remove('hidden');
                document.getElementById('loadingIndicator').classList.add('hidden');
                countDisplay.textContent = '0';
                return;
            }

            noRestaurants.classList.add('hidden');
            document.getElementById('loadingIndicator').classList.add('hidden');
            countDisplay.textContent = restaurants.length;

            restaurants.forEach(doc => {
                const data = doc.data();
                const docId = doc.id;
                currentRestaurants[docId] = data; // บันทึกข้อมูลเพื่อใช้ใน Modal

                const likeCount = data.foods.filter(f => f.status === 'like').length;
                const dislikeCount = data.foods.filter(f => f.status === 'dislike').length;
                const locationText = data.lat ? `Lat: ${data.lat.toFixed(4)}, Lng: ${data.lng.toFixed(4)}` : 'ไม่มีตำแหน่ง';

                const restaurantElement = `
                    <div class="bg-gray-50 p-4 rounded-lg border border-gray-200 hover:bg-gray-100 transition duration-150 flex justify-between items-center">
                        <div>
                            <p class="text-lg font-semibold text-indigo-600">${data.name}</p>
                            <p class="text-xs text-gray-500 mb-1">${locationText}</p>
                            <div class="flex space-x-3 text-sm mt-1">
                                <span class="flex items-center text-pink-500 font-medium">❤️ ${likeCount}</span>
                                <span class="flex items-center text-red-500 font-medium">🤢 ${dislikeCount}</span>
                            </div>
                        </div>
                        <button onclick="openFoodModal('${docId}')" class="flex-shrink-0 bg-indigo-500 text-white text-sm px-3 py-1 rounded-full hover:bg-indigo-600 shadow-md">
                            จัดการรายการอาหาร
                        </button>
                    </div>
                `;
                listContainer.innerHTML += restaurantElement;
            });
        }


        // --- Firebase Initialization and Auth ---

        /** เริ่มต้น Firebase และตั้งค่า Auth */
        const initializeFirebase = async () => {
            try {
                if (Object.keys(firebaseConfig).length === 0) {
                     document.getElementById('authStatus').textContent = 'Firebase Config Not Found. Using Anonymous Login.';
                } else {
                    const app = initializeApp(firebaseConfig);
                    db = getFirestore(app);
                    auth = getAuth(app);
                }

                // 1. Sign In (using custom token if available, otherwise anonymous)
                if (initialAuthToken) {
                    await signInWithCustomToken(auth, initialAuthToken);
                } else {
                    await signInAnonymously(auth);
                }

            } catch (e) {
                console.error("Firebase Initialization/Auth Error:", e);
                showMessage("ไม่สามารถเชื่อมต่อ Firebase ได้: " + e.message, true);
                document.getElementById('authStatus').textContent = 'ข้อผิดพลาดในการตรวจสอบสิทธิ์';
            }
        }

        /** Listener สำหรับสถานะผู้ใช้ */
        const setupAuthListener = () => {
            onAuthStateChanged(auth, (user) => {
                if (user) {
                    userId = user.uid;
                    document.getElementById('authStatus').textContent = `ผู้ใช้: ${userId}`;
                    setupRestaurantListener(); // เมื่อได้ userId แล้ว ค่อยเริ่มดึงข้อมูล
                } else {
                    userId = null;
                    document.getElementById('authStatus').textContent = 'สถานะ: ไม่อนุญาต';
                    // Clear list if user logs out unexpectedly
                    document.getElementById('restaurantList').innerHTML = '<p class="text-center text-gray-500">กรุณารอการตรวจสอบสิทธิ์</p>';
                }
            });
        }

        /** Listener สำหรับข้อมูลร้านอาหาร */
        const setupRestaurantListener = () => {
            if (!db || !userId) return;

            const restaurantsRef = collection(db, getRestaurantCollectionPath());
            const q = query(restaurantsRef);

            onSnapshot(q, (snapshot) => {
                const restaurants = [];
                snapshot.forEach((doc) => {
                    restaurants.push(doc);
                });
                renderRestaurants(restaurants);

                // หาก Modal เปิดอยู่ ให้ทำการอัปเดตรายการอาหารใน Modal ด้วยข้อมูลล่าสุด
                if (document.getElementById('foodModal').style.display === 'flex' && currentRestaurantDocId) {
                    const latestData = currentRestaurants[currentRestaurantDocId];
                    if (latestData) {
                        renderFoodItems(latestData.foods);
                    }
                }
            }, (error) => {
                console.error("Firestore Listener Error:", error);
                showMessage("เกิดข้อผิดพลาดในการดึงข้อมูลแบบเรียลไทม์: " + error.message, true);
            });
        }

        // --- Main execution flow ---
        window.onload = () => {
            // เริ่มต้นระบบ GPS ทันที
            getGeolocation();

            // เริ่มต้น Firebase และ Auth
            if (typeof getAuth !== 'undefined') {
                 initializeFirebase().then(setupAuthListener);
            } else {
                showMessage('Firebase SDKs โหลดไม่สำเร็จ', true);
            }
        };

    </script>
</body>
</html>
