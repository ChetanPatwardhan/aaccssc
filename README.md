
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Panel Layout</title>
    <style>
        body {
            display: flex;
            margin: 0;
            font-family: Arial, sans-serif;
            height: 100vh;
            overflow: hidden;
            background-color: #f4f4f4;
        } 
        .panel {
            padding: 20px;
            box-sizing: border-box;
            overflow-y: auto;
        }
        .left-panel {
            width: 40%;
            background-color: #f4f4f4;
            padding-left: 5%;
        }
        .right-panel {
            width:35%;
            background-color: #f4f4f4;
            padding-left: 7%;
        }
        h1 {
            font-size: 20px;
            margin-top: 0;
        }
        .form-group {
            margin-bottom: 15px;
            width: 25%;
        }
        label {
            display: block;
            margin-bottom: 5px;
        }
        select, button, input {
            width: calc(100% - 20px);
            padding: 8px;
            box-sizing: border-box;
            margin-bottom: 10px;
        }
        button {
            background-color: #007bff;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
        .value-display {
            font-weight: bold;
        }
        .mission-section {
            margin-top: 20px;
        }.mission-item, .unit-item, .area-item {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }
        .mission-item label, .unit-item label, .area-item label {
            flex: 1;
            min-width: 150px;
        }
        .mission-item input, .unit-item input, .area-item input {
            flex: 2;
            margin-right: 10px;
        }
        .mission-item button, .unit-item button, .area-item button {
            flex: 1;
        }
        .circle-button {
            width: 20px;
            height: 20px;
            border-radius: 50%;
            border: 2px solid #000;
            background-color: #fff;
            margin-right: 10px;
            cursor: pointer;
            text-align: center;
        }
        .circle-button.active {
            background-color: red;
        }
        

        
    </style>
</head>
<body>
    <div class="left-panel panel">
        <h4>General</h4>
        <div class="form-group">
            <label for="theme">Theme</label>
            <select id="theme">
                <option value="light">Light</option>
                <option value="dark">Dark</option>
                <option value="solarized">Solarized</option>
            </select>
        </div>
        <div class="form-group">
            <label for="language">Language</label>
            <select id="language">
                <option value="en">English</option>
                <option value="es">Spanish</option>
                <option value="fr">French</option>
                <option value="de">German</option>
            </select>
        </div>
        <div class="form-group">
            <button id="sound">Sound: Off</button>
        </div>
        
        <div class="mission-section">
            <h4>Mission Default Values</h4>
            <div class="mission-item">
                <label for="wp-speed">WP Speed (m/s)</label>
                <input type="number" id="wp-speed" value="0" min="0" max="300">
                <button onclick="increaseValue('wp-speed')">Increase WP Speed</button>
            </div>
            <div class="mission-item">
                <label for="wp-altitude">WP Altitude (m)</label>
                <input type="number" id="wp-altitude" value="0" min="0" max="300">
                <button onclick="increaseValue('wp-altitude')">Increase WP Altitude</button>
            </div>
            <div class="mission-item">
                <label for="rails-speed">Rails Speed (m/s)</label>
                <input type="number" id="rails-speed" value="0" min="0" max="300">
                <button onclick="increaseValue('rails-speed')">Increase Rails Speed</button>
            </div>
            <div class="mission-item">
                <label for="rails-altitude">Rails Altitude (m)</label>
                <input type="number" id="rails-altitude" value="0" min="0" max="300">
                <button onclick="increaseValue('rails-altitude')">Increase Rails Altitude</button>
            </div>
            <div class="mission-item">
                <label for="track-family-interval">Track Family Interval (m/s)</label>
                <input type="number" id="track-family-interval" value="0" min="0" max="300">
                <button onclick="increaseValue('track-family-interval')">Increase Track Family Interval</button>
            </div>
            <div class="mission-item">
                <label for="circle-speed">Circle Speed (m/s)</label>
                <input type="number" id="circle-speed" value="0" min="0" max="300">
                <button onclick="increaseValue('circle-speed')">Increase Circle Speed</button>
            </div>
            <div class="mission-item">
                <label for="circle-altitude">Circle Altitude (m)</label>
                <input type="number" id="circle-altitude" value="0" min="0" max="300">
                <button onclick="increaseValue('circle-altitude')">Increase Circle Altitude</button>
            </div>
            <div class="mission-item">
                <label for="timeout">Timeout (s)</label>
                <input type="number" id="timeout" value="0" min="0" max="300">
                <button onclick="increaseValue('timeout')">Increase Timeout</button>
            </div>
        </div>
    </div>
    <div class="right-panel panel">
        <h4>Units</h4>
        <div class="unit-item">
            <label for="distance">Distance (m)</label>
            <select id="distance">
                <option value="en">m</option>
                <option value="es">feet</option>
            </select>
        </div>
        <div class="unit-item">
            <label for="coordinate">Coordinate</label>
            <select id="coordinate">
                <option value="en">D</option>
                <option value="es">D</option>
                <option value="es">DWH</option>
                <option value="es">DM</option>
                <option value="es">DMWH</option>
                <option value="es">DMS</option>
                <option value="es">DMSWH</option>
            </select>
        </div>
        <div class="unit-item">
            <label for="speed">Speed (m/s)</label>
            <select id="speed">
                <option value="en">m/s</option>
                <option value="es">knots</option>
            </select>
        </div>

        <h4>Area Default Values</h4>
        <div class="area-item">
            <label for="exclusion">Exclusion</label>
            <label for="exclusion">Border</label>
            <div class="circle-button" onclick="toggleButton(this)"></div>
            <label for="exclusion">Fill</label>
            <div class="circle-button" onclick="toggleButton(this)"></div>
        </div>
        <div class="area-item">
            <label for="containment">Containment</label>
            <label for="containment">Border</label>
            <div class="circle-button" onclick="toggleButton(this)"></div>
            <label for="containment">Fill</label>
            <div class="circle-button" onclick="toggleButton(this)"></div>
        </div>
        <div class="area-item">
            <label for="min-depth">Min Depth</label>
            <label for="min-depth">Border</label>
            <div class="circle-button" onclick="toggleButton(this)"></div>
            <label for="min-depth">Fill</label>
            <div class="circle-button" onclick="toggleButton(this)"></div>
        </div>
        <div class="area-item">
            <label for="max-depth">Max Depth</label>
            <label for="max-depth">Border</label>
            <div class="circle-button" onclick="toggleButton(this)"></div>
            <label for="max-depth">Fill</label>
            <div class="circle-button" onclick="toggleButton(this)"></div>
        </div>
        <div class="area-item">
            <label for="contacts">Contacts</label>
            <div class="circle-button" onclick="toggleButton(this)"></div>
        </div>
        
    </div>

    <script>
        // JavaScript to handle the circle button toggle
        function toggleButton(button) {
            button.classList.toggle('active');
        }
    </script>
    </div>

    <script>
        // JavaScript to handle unit updates can go here
    </script>
    </div>

    <script>
        // JavaScript to toggle the sound button text
        document.getElementById('sound').addEventListener('click', function() {
            var button = this;
            if (button.textContent === 'Sound: Off') {
                button.textContent = 'Sound: On';
                // Add logic here to enable sound if needed
            } else {
                button.textContent = 'Sound: Off';
                // Add logic here to disable sound if needed
            }
        });

        // JavaScript to increase values for mission default parameters
        function increaseValue(id) {
            var element = document.getElementById(id);
            var currentValue = parseInt(element.value);
            if (currentValue < 300) { // Ensure the value does not exceed 300
                element.value = currentValue + 10; // Increase by 10 (or adjust as needed)
            }
        }
    </script>
</body>
</html>
