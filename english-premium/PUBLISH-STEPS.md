# Publish English page (Mo approved: "Publish english", 9 Nov 2026 04:52)

Do NOT shut down or sleep the laptop. Do not change /anmeldung/, /schwimmstunden/, the smo-booking plugin, prices, or any other page. Never enter passwords; ask Mo to log in if needed.

Page: WordPress page 1269, https://schwimmschulemo.at/english/ — one Elementor HTML widget (data-id 61365ea). Same process as the landing/gratkorn publishes.

1. Get the widget's exact raw HTML. Save it to ClaudeCode\english-premium\backup-1269-original.html. Check it is complete (contains `<header class="site-header" id="moEnHeader">`, ends with the Winter-Pass scripts using `data-wp-places` / `winter-places`).
2. Build ClaudeCode\english-premium\new-1269.html from the backup:
   a. Find the first `</header>` after `id="moEnHeader"`.
   b. Find the main script that starts `<script>` + newline + `(function () {` + newline + `  var root = document.querySelector('.mo-en-page');`.
   c. Replace everything BETWEEN (a) and (b) with the full contents of ClaudeCode\english-premium\sections.html. Keep the header, that main script and everything after it unchanged.
   d. Check new file: exactly one `class="enp-hero"`, one `id="courses"`, one `id="winter-pass"`, one `id="kids"`, one `id="adults"`, one `id="curriculum"`, one `id="contact"`, one `class="smo-bk"`; no `id="course-finder"`, no `id="en-panel-1"`, no `class="t-track"`.
3. Put new-1269.html into the widget and Update page 1269. Do not change SmartCrawl title/description.
4. Purge LiteSpeed (all) and Hummingbird caches (Hostinger CDN if available).
5. Check as a normal visitor (new incognito window, desktop 1440 and phone width): navy hero "English swimming lessons in Graz – private for kids from 3 and adults" with trial card (€35/€50/€50/€60); price table with 4 cards + Winter Pass card; Coach Mo photo loads; booking widget loads in English; FAQ opens; App pill hidden; trial link opens /buchen/?lang=en&kurs=flex&paket=28 with the trial selected. Do NOT book or pay.
6. Report: backup and new file paths, what you checked, any problem. If anything breaks, restore backup-1269-original.html immediately and report.
