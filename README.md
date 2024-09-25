<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Spell Book</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #121212;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        /* Book Container */
        .spellbook-container {
            width: 800px;
            height: 500px;
            background-image: url('https://t4.ftcdn.net/jpg/00/73/60/59/360_F_73605967_4rpzIVWqVR6HxAVcC2mar6H8erHiBIW5.jpg');
            background-size: cover;
            position: relative;
            border: 5px solid #8a623d;
            border-radius: 10px;
            box-shadow: 0px 0px 50px 5px rgba(0, 0, 0, 0.7);
        }

        /* Inner Pages */
        .page {
            width: 350px;
            height: 450px;
            background: rgba(255, 255, 255, 0.9);
            position: absolute;
            top: 25px;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0px 0px 5px 2px rgba(0, 0, 0, 0.3);
            overflow-y: auto;
        }

        .page:nth-child(odd) {
            left: 20px;
        }

        .page:nth-child(even) {
            right: 20px;
        }

        h2 {
            font-size: 24px;
            margin-top: 0;
            color: #4a2d1b;
        }

        p {
            font-size: 18px;
            line-height: 1.5;
            color: #333;
        }

        .spell {
            margin-bottom: 20px;
        }

        .spell-name {
            font-weight: bold;
            color: #8a623d;
        }

        /* Navigation Buttons */
        .navigation {
            position: absolute;
            bottom: 20px;
            width: 100%;
            text-align: center;
        }

        .nav-btn {
            background-color: #8a623d;
            border: none;
            color: white;
            padding: 10px 20px;
            margin: 10px;
            cursor: pointer;
            border-radius: 5px;
            font-size: 18px;
        }

        .nav-btn:hover {
            background-color: #4a2d1b;
        }

        .hidden {
            display: none;
        }
    </style>
</head>
<body>

<div class="spellbook-container">
    <!-- Left Page -->
    <div id="page1" class="page">
        <h2>Arcane Spells</h2>
        <div class="spell">
            <p class="spell-name">Arcane Nova</p>
            <p><strong>Type:</strong> Area Burst | <strong>Element:</strong> Pure Magic | <strong>Range:</strong> Mid-Range, AoE</p>
            <p>The caster claps their hands together, generating a small, concentrated orb of pure magical energy. The orb pulses and expands outward in a massive explosion of pure arcane force, dealing heavy damage to all nearby enemies.</p>
           <p><strong>Effect:</strong> Disrupts magical constructs and nullifies lesser spells in the area</p>
        </div>
        <div class="spell">
            <p class="spell-name">Dimensional Rift</p>
            <p><strong>Type:</strong> Portal Magic | <strong>Element:</strong> Arcane | <strong>Range:</strong> Infinite</p>
            <p>The caster traces a rune in the air, causing a tear in reality. This creates a rift that can teleport the caster or their allies to any known location or even trap enemies in pocket dimensions.</p>
            <p><strong>Effect:</strong> Functions as both teleportation and banishment.</p>
        </div>
            <div> class="spell">
            <p class="spell-name">Mana Detonation</p>
            <p><strong>Type:</strong> Portal Magic | <strong>Element:</strong> Arcane | <strong>Range:</strong> Single Target, High Damage</p>
            <p>The caster channels pure mana into a target, causing their magical reserves to overload and explode. The explosion deals massive damage and disrupts any spellcasting abilities.</p>
            <p><strong>Effect:</strong> Overloads the magical energy of a target.</p>
        </div>
    </div>


    <!-- Right Page -->
    <div id="page2" class="page hidden">
        <h2>Fire Spells</h2>
        <div class="spell">
            <p class="spell-name">Phoenix Burst</p>
            <p><strong>Type:</strong> Summoning/Offensive | <strong>Element:</strong> Fire | <strong>Range:</strong> Wide AoE</p>
            <p>The caster conjures a giant phoenix made of flames...</p>
        </div>
        <div class="spell">
            <p class="spell-name">Molten Surge</p>
            <p><strong>Type:</strong> Offensive/Utility | <strong>Element:</strong> Fire/Earth | <strong>Range:</strong> Mid-Range</p>
            <p>The caster slams their hands into the ground, causing molten lava to surge up...</p>
        </div>
    </div>

    <div class="navigation">
        <button class="nav-btn" onclick="prevPage()">Previous</button>
        <button class="nav-btn" onclick="nextPage()">Next</button>
    </div>
</div>

<script>
    let currentPage = 1;

    function showPage(pageNum) {
        document.querySelectorAll('.page').forEach(page => page.classList.add('hidden'));
        document.getElementById('page' + pageNum).classList.remove('hidden');
    }

    function nextPage() {
        if (currentPage < 2) { // Total number of pages
            currentPage++;
            showPage(currentPage);
        }
    }

    function prevPage() {
        if (currentPage > 1) {
            currentPage--;
            showPage(currentPage);
        }
    }
</script>

</body>
