<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>מערכת מומחה מקצועית - זכאות לפנסיה לפי צווי הרחבה- היחידה ליחסי עבודה</title>
    <style>
        :root {
            --primary-color: #1e3a8a;
            --secondary-color: #3b82f6;
            --accent-color: #f59e0b;
            --bg-color: #f8fafc;
            --card-bg: #ffffff;
            --text-main: #1e293b;
            --text-muted: #64748b;
            --border-color: #e2e8f0;
            --success-color: #10b981;
            --warning-color: #ef4444;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            line-height: 1.6;
            padding-bottom: 60px;
        }

        header {
            background-color: var(--primary-color);
            color: white;
            padding: 20px;
            text-align: center;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
        }

        header h1 {
            font-size: 24px;
            margin-bottom: 5px;
        }

        header p {
            font-size: 14px;
            opacity: 0.9;
        }

        nav {
            display: flex;
            justify-content: center;
            background-color: var(--card-bg);
            border-bottom: 1px solid var(--border-color);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        nav button {
            background: none;
            border: none;
            padding: 15px 25px;
            font-size: 16px;
            font-weight: 600;
            color: var(--text-muted);
            cursor: pointer;
            transition: all 0.3s ease;
            border-bottom: 3px solid transparent;
        }

        nav button:hover {
            color: var(--secondary-color);
        }

        nav button.active {
            color: var(--primary-color);
            border-bottom-color: var(--primary-color);
        }

        main {
            max-width: 1200px;
            margin: 30px auto;
            padding: 0 20px;
        }

        .page {
            display: none;
        }

        .page.active {
            display: block;
        }

        .card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 25px;
            margin-bottom: 25px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.05);
        }

        h2 {
            color: var(--primary-color);
            margin-bottom: 20px;
            border-bottom: 2px solid var(--border-color);
            padding-bottom: 8px;
            font-size: 20px;
        }

        h3 {
            color: var(--secondary-color);
            margin: 15px 0 10px 0;
            font-size: 17px;
        }

        .form-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
        }

        .form-group.full-width {
            grid-column: 1 / -1;
        }

        label {
            font-weight: 600;
            margin-bottom: 6px;
            font-size: 14px;
        }

        label .required {
            color: var(--warning-color);
            margin-right: 4px;
        }

        input, select, textarea {
            padding: 10px;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            font-size: 14px;
            background-color: #fafafa;
            transition: border-color 0.2s;
        }

        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: var(--secondary-color);
            background-color: #fff;
        }

        .table-container {
            overflow-x: auto;
            margin: 15px 0;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            text-align: right;
        }

        table th, table td {
            padding: 12px;
            border: 1px solid var(--border-color);
            font-size: 14px;
        }

        table th {
            background-color: #f1f5f9;
            font-weight: 600;
        }

        .btn {
            background-color: var(--secondary-color);
            color: white;
            border: none;
            padding: 12px 24px;
            font-size: 16px;
            font-weight: 600;
            border-radius: 6px;
            cursor: pointer;
            transition: background-color 0.2s;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .btn:hover {
            background-color: #2563eb;
        }

        .btn-primary {
            background-color: var(--primary-color);
            font-size: 18px;
            padding: 15px 30px;
            width: 100%;
        }

        .btn-primary:hover {
            background-color: #172554;
        }

        .btn-success { background-color: var(--success-color); }
        .btn-success:hover { background-color: #059669; }

        .btn-danger { background-color: var(--warning-color); padding: 6px 12px; font-size: 13px;}
        .btn-danger:hover { background-color: #dc2626; }

        .alert-info-box {
            background-color: #eff6ff;
            border-right: 4px solid var(--secondary-color);
            padding: 15px;
            border-radius: 4px;
            margin-bottom: 20px;
            font-size: 14px;
        }

        .alert-warning-box {
            background-color: #fffbeb;
            border-right: 4px solid var(--accent-color);
            padding: 15px;
            border-radius: 4px;
            margin-bottom: 20px;
            font-size: 14px;
            color: #92400e;
        }

        .report-section {
            margin-bottom: 25px;
            padding-bottom: 15px;
            border-bottom: 1px dashed var(--border-color);
        }

        .report-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
            gap: 15px;
            background: #f8fafc;
            padding: 15px;
            border-radius: 6px;
        }

        .report-item span {
            display: block;
        }

        .report-item .lbl {
            font-weight: 600;
            font-size: 13px;
            color: var(--text-muted);
        }

        .report-item .val {
            font-size: 15px;
            font-weight: 500;
        }

        .action-bar {
            display: flex;
            gap: 15px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        .search-box {
            margin-bottom: 20px;
            width: 100%;
            max-width: 400px;
        }

        .library-grid {
            display: grid;
            grid-template-columns: 1fr 3fr;
            gap: 20px;
        }

        @media (max-width: 768px) {
            .library-grid {
                grid-template-columns: 1fr;
            }
        }

        .lib-menu {
            border-left: 1px solid var(--border-color);
            max-height: 700px;
            overflow-y: auto;
            padding-left: 10px;
        }

        .lib-menu-item {
            display: block;
            width: 100%;
            text-align: right;
            padding: 12px;
            background: none;
            border: 1px solid transparent;
            border-radius: 4px;
            cursor: pointer;
            font-size: 14px;
            font-weight: 500;
            transition: all 0.2s;
            margin-bottom: 5px;
        }

        .lib-menu-item:hover, .lib-menu-item.active {
            background-color: #f1f5f9;
            color: var(--primary-color);
            font-weight: 600;
        }

        .lib-content {
            background: #fff;
            padding: 20px;
            border-radius: 6px;
        }

        footer {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background-color: #0f172a;
            color: #94a3b8;
            padding: 10px;
            text-align: center;
            font-size: 11px;
            border-top: 1px solid #1e293b;
            z-index: 1000;
        }

        footer .highlight {
            color: #f8fafc;
            font-weight: 500;
        }

        .badge {
            display: inline-block;
            padding: 3px 8px;
            font-size: 12px;
            font-weight: 600;
            border-radius: 4px;
            background-color: #e2e8f0;
            color: var(--text-main);
        }

        .badge-warning { background-color: #fef3c7; color: #92400e; }
        .badge-success { background-color: #d1fae5; color: #065f46; }

        @media print {
            nav, header, footer, .action-bar, .no-print {
                display: none !important;
            }
            body {
                padding: 0;
                background: white;
            }
            .card {
                border: none;
                box-shadow: none;
                padding: 0;
            }
            .page {
                display: block !important;
            }
        }
    </style>
</head>
<body>

    <header>
        <h1>הזכאות לפנסיה לפי צווי הרחבה – היחידה ליחסי עבודה</h1>
        <p>מערכת מומחה מקצועית מקיפה לניתוח ותחולת צווי הרחבה ענפיים במשק והזכות לביטוח פנסיה- הוכן על ידי עו"ד אבראהים כילאני, ראש צוות ייעוץ משפטי (יחסי עבודה) - היחידה ליחסי עבודה - לשימוש פנימי בלבד</p>
    </header>

    <nav>
        <button id="btn-input" class="active" onclick="switchPage('input', event)">סימולטור ניתוח משפטי</button>
        <button id="btn-output" onclick="switchPage('output', event)">חוות דעת שהופקה</button>
        <button id="btn-library" onclick="switchPage('library', event)">ספריית צווי הרחבה</button>
    </nav>

    <main>
        
        <section id="page-input" class="page active">
            <div class="card">
                <h2>נתוני מזהים של המעסיק והעסק</h2>
                <div class="form-grid">
                    <div class="form-group">
                        <label for="compName">שם המעסיק / חברה</label>
                        <input type="text" id="compName" placeholder="לדוגמה: משה כהן הובלות בע&quot;מ">
                    </div>
                    <div class="form-group">
                        <label for="mainSector">תחום פעילות כללי (סיווג משוער)</label>
                        <select id="mainSector" onchange="handleSectorChange()">
                            <option value="">-- בחר תועד מועדף --</option>
                            <option value="בנייה">בנייה, תשתיות, צמ&quot;ה ושיפוצים</option>
                            <option value="הובלה">הובלה (רכבי משא מעל 4 טון)</option>
                            <option value="חקלאות">חקלאות, גננות נוי ומשתלות</option>
                            <option value="רשתות שיווק">רשתות שיווק מזון</option>
                            <option value="ניקיון">ניקיון ותחזוקה</option>
                            <option value="שמירה">שמירה ואבטחה</option>
                            <option value="מוקד">מוקד וסיור</option>
                            <option value="מתכת">מתכת, חשמל ואלקטרוניקה (עד 20 עובדים)</option>
                            <option value="מלונאות">מלונאות ואירוח</option>
                            <option value="היסעים">היסעים (נוסעים באוטובוסים/מיניבוס)</option>
                            <option value="הסעדה">שירותי הסעדה, אולמות ואירועים</option>
                            <option value="כוח אדם">אספקת שירותי כוח אדם</option>
                            <option value="מוסכים">מוסכים ובתי מלאכה לרכב</option>
                            <option value="קולנוע">קולנוע, טלוויזיה והפקות</option>
                            <option value="יהלומים">ענף היהלומים</option>
                            <option value="יבוא מסחר">יבוא, מסחר ושירותים</option>
                            <option value="תעשייה">תעשייה (כללי - מעל 20 עובדים)</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="empCount"><span class="required">*</span> מספר עובדים כולל בעסק</label>
                        <input type="number" id="empCount" placeholder="חובה לצורך חישוב והכרעת סייגים">
                    </div>
                    <div class="form-group">
                        <label for="numBranches">מספר סניפים</label>
                        <input type="number" id="numBranches" placeholder="רלוונטי במיוחד לרשתות שיווק">
                    </div>
                    <div class="form-group">
                        <label for="turnover">מחזור פעילות שנתי משוער (ש&quot;ח)</label>
                        <input type="number" id="turnover" placeholder="אופציונלי">
                    </div>
                </div>

                <div class="form-group full-width" style="margin-bottom: 15px;">
                    <label for="businessDesc"><span class="required">*</span> תיאור מלא של פעילות העסק, מוצרים ושירותים</label>
                    <textarea id="businessDesc" rows="4" placeholder="תאר כאן בפירוט את עיסוקו המרכזי של המעסיק. מנוע ההחלטה ינתח שדה זה באופן מהותי לצורך חילוץ צו ההרחבה המתאים גם אם השדות האחרים ריקים..."></textarea>
                </div>
            </div>

            <div class="card">
                <h2>חלוקת כוח אדם פנימית (מבחן עיקר העיסוק והרכב עובדים)</h2>
                <p style="font-size: 13px; color: var(--text-muted); margin-bottom: 10px;">
                    הזן את חלוקת העובדים לפי מחלקות/עיסוקים. המנוע ישתמש בנתונים אלו לבחינת מבחני הפסיקה של עיקר הפעילות.
                </p>
                <div class="table-container">
                    <table id="staffTable">
                        <thead>
                            <tr>
                                <th>תחום פעילות / מחלקה בעסק</th>
                                <th>מספר עובדים במחלקה</th>
                                <th>אחוז מכוח האדם (%)</th>
                                <th class="no-print">פעולות</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td><input type="text" value="גרעין הפעילות המרכזי" style="width:100%"></td>
                                <td><input type="number" value="" oninput="calcStaffPercentages()" style="width:100%"></td>
                                <td><input type="number" readonly class="pct-field" style="width:100%"></td>
                                <td class="no-print"><button class="btn btn-danger" onclick="deleteRow(this)">מחק</button></td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                <button class="btn btn-success no-print" onclick="addStaffRow()">הוסף תחום/מחלקה</button>
            </div>

            <div class="card">
                <h2>נתוני העובד הספציפי שנבחן</h2>
                <div class="form-grid">
                    <div class="form-group">
                        <label for="workerRole">תפקיד העובד</label>
                        <input type="text" id="workerRole" placeholder="לדוגמה: מנופאי, נהג, מחסנאי, מנקה">
                    </div>
                    <div class="form-group">
                        <label for="workerDept">מחלקה / שיוך ארגוני</label>
                        <input type="text" id="workerDept" placeholder="לדוגמה: תפעול, אדמיניסטרציה">
                    </div>
                    <div class="form-group">
                        <label for="workerSeniority">ותק בעבודה (בחודשים)</label>
                        <input type="number" id="workerSeniority" placeholder="מספר חודשי עבודה">
                    </div>
                    <div class="form-group">
                        <label for="workerAge">גיל העובד</label>
                        <input type="number" id="workerAge" placeholder="בשנים">
                    </div>
                    <div class="form-group">
                        <label for="pensionStatus">סטטוס ביטוחי פנסיוני קודם</label>
                        <select id="pensionStatus">
                            <option value="unknown">לא ידוע</option>
                            <option value="active">יש הסדר פנסיוני פעיל (הפרשות קודמות)</option>
                            <option value="none">אין הסדר פנסיוני פעיל כלל</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="employmentType">סוג העסקה</label>
                        <select id="employmentType">
                            <option value="חודשי">חודשי / גלובלי</option>
                            <option value="שעתי">שעתי / יומי</option>
                        </select>
                    </div>
                </div>

                <h3>פירוט רכיבי שכר חודשיים (בשקלים)</h3>
                <div class="form-grid">
                    <div class="form-group">
                        <label for="salaryBase">שכר יסוד / תעריפי</label>
                        <input type="number" id="salaryBase" placeholder="0">
                    </div>
                    <div class="form-group">
                        <label for="salaryCommissions">עמלות מכירה</label>
                        <input type="number" id="salaryCommissions" placeholder="0">
                    </div>
                    <div class="form-group">
                        <label for="salaryPremiums">פרמיות (מדודות / מותנות)</label>
                        <input type="number" id="salaryPremiums" placeholder="0">
                    </div>
                    <div class="form-group">
                        <label for="salaryBonuses">בונוסים / מענקים שנתיים</label>
                        <input type="number" id="salaryBonuses" placeholder="0">
                    </div>
                    <div class="form-group">
                        <label for="salaryAllowances">תוספות שכר גלובליות / קבועות</label>
                        <input type="number" id="salaryAllowances" placeholder="0">
                    </div>
                    <div class="form-group">
                        <label for="salaryExpenses">החזרי הוצאות (נסיעות, אש&quot;ל)</label>
                        <input type="number" id="salaryExpenses" placeholder="0">
                    </div>
                </div>
            </div>

            <button class="btn btn-primary no-print" onclick="generateLegalOpinion()">
                הפעל מנוע החלטה והפק חוות דעת מנומקת
            </button>
        </section>

        <section id="page-output" class="page">
            <div class="action-bar no-print">
                <button class="btn btn-success" onclick="copyOpinion()">העתק חוות דעת לקליפבורד</button>
                <button class="btn" onclick="window.print()">הדפסה או שמירה כ-PDF</button>
                <button class="btn btn-danger" onclick="switchPage('input', event)" style="background-color: var(--text-muted)">חזרה לסימולטור</button>
            </div>

            <div id="opinion-container" class="card">
                <p style="text-align:center; color: var(--text-muted);">טרם הופקה חוות דעת. מלא את נתוני המינימום בסימולטור ולחץ על כפתור ההפעלה.</p>
            </div>
        </section>

        <section id="page-library" class="page">
            <div class="card">
                <h2>ספריית צווי הרחבה ענפיים מובנית</h2>
                <div class="search-box no-print">
                    <input type="text" id="libSearch" onkeyup="filterLibrary()" placeholder="חפש ענף, מילת מפתח או פסיקה..." style="width: 100%">
                </div>
                
                <div class="library-grid">
                    <div class="lib-menu" id="libMenu">
                        </div>
                    <div class="lib-content" id="libContent">
                        <p style="color: var(--text-muted); text-align: center;">בחר ענף מהתפריט הימני לצפייה בפרטים המלאים ובסעיפי החוק.</p>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <footer>
        <p>
            <span class="highlight">הזכאות לפנסיה לפי צווי הרחבה – היחידה ליחסי עבודה</span> | 
            הוכן, רוכז ונערך על ידי <span class="highlight">עו"ד אבראהים כילאני</span>, ראש צוות ייעוץ משפטי (יחסי עבודה). | 
            <span class="highlight">לשימוש פנימי בלבד.</span> | 
            כל הזכויות שמורות ל<span class="highlight">עו"ד אבראהים כילאני</span>.
        </p>
    </footer>

    <script>
        // --- מאגר המידע המלא והמשולב של צווי ההרחבה  ---
        const libraryData = {
           
 "בנייה": {
                name: "בנייה, תשתיות, צמ\"ה ושיפוצים",
                orders: "צווי 2015, נספח מנופאים 2017, צו עדכון 2018. צו 2015 ביטל את צו 2010 הישן.",
                employerDef: "כל מעסיק בתחומי הבינוי, התשתיות, עבודות ציבוריות, הנדסה אזרחית, צמ\"ה ושיפוצים (ענפים ראשיים 41-43 לסיווג הלמ\"ס).",
                workerDef: "כל עובד ומנהל עבודה באתר בנייה בתפקיד שאינו משרדי, לרבות תת-הגדרה ייחודית למנופאים (מפעילי עגורן צריח).",
                eligibility: "זכאות מיידית מיום תחילת העבודה ללא תקופת המתנה.",
                rates: "תגמולי עובד: 6.6%, תגמולי מעסיק: 7.1%, פיצויים: 6% או 8.33% (לפי צו 2018).",
                insuredSalary: "השכר התעריפי המוגדר בטבלאות לפי הדרגות (1-8 לעובדים). אינו כולל פרמיות אמיתיות, אש\"ל או החזרי הוצאות.",
                exceptions: "עובדי משרד, אדמיניסטרציה, הנהלת חשבונות ותפקידי מטה שאינם באתרי הבנייה עצמם.",
                jurisprudence: "בר\"ע (ארצי) 59618-01-23 א. חשמל כרמיאל בע\"מ - אולג פונטוס (02.03.2023) בית הדין הארצי לעבודה קבע כי פעילויות של הבינוי, יסווגו כפעילויות המתבצעות בענף הבנייה רק כל עוד הן חלק מתהליך של מיזם בנייה. כלומר, אם הפעולות מתבצעות אגב מתן שירותי תחזוקה למפעל קיים, מפעל זה אינו מהווה אתר בנייה לצורך תחולת צו ההרחבה בענף הבנייה.<br> דוגמה קונקרטית: במקרה שבו חברה עוסקת בייצור והתקנת תעלות מיזוג אוויר, נבחנה השאלה האם חל עליה צו הרחבה בענף הבנייה (התקנת מערכות מיזוג אוויר) או בענף המתכת (ייצור תעלות פח). בית הדין קבע כי יש לבחון מהו עיקר עיסוקה של החברה. אם הפעילות המשמעותית היא התקנת תעלות פח למערכות מיזוג אוויר והרכבתן באתרים שונים, אזי חל צו ההרחבה בענף הבנייה. זאת, למרות שפעילות ייצור תעלות פח כלולה בסיווג האחיד בענף התעשייה. ההכרעה תלויה בתשתית הראייתית שהוצגה ובפעילות הדומיננטית. סע\"ש (אזורי ת\"א) 44938-07-19 אלכסיי שניידרמן - המומחים למיזוג אויר (1994) בע\"מ (31.10.2022). <br>דוגמה נוספת - התקנת מעליות: חברה העוסקת בהתקנת מעליות מסווגת בסיווג האחיד תחת ענף ראשי 45 -בנייה, תת ענף 4540 - התקנת מעליות ומיתקני הרמה. אולם, גם במקרה זה, אם העובד לא הוכיח כי עבד באתר בנייה כהגדרתו בצו, אלא בבניין קיים, צו ההרחבה בענף הבנייה לא יחול. סע\"ש (אזורי ת\"א) 63562-07-19 דמיטרי קריבצוב - א.א. ברוק מעליות בע\"מ (09.05.2021).<br>ע\"ע (ארצי) 18496-12-20 אלמא הגוס - עד - ליאון הנדסה בניה וקבלנות בע\"מ (12.01.2023): החלטה זו דנה בעובד זר שהועסק בעבודות בניין ושמירה. בית הדין הארצי קיבל את ערעור העובד וחייב את המעסיקים בתשלומים לפי צו ההרחבה בענף הבנייה, תוך קביעה כי מאפייני השעות מובילים למסקנה כי לא מדובר בשעות עבודה אלא בשעות שהייה.",
                qna: [
                    {q: "האם מנהל עבודה זכאי להפרשות לפי צו זה?", a: "כן, מנהלי עבודה באתרי בנייה נכללים במפורש בצו (דרגות 1-7 למנהלי עבודה) וזכאים לתנאיו."},
                    {q: "מהן ההוראות המיוחדות למנופאים?", a: "זכאים לתוספת מאמץ בסך 3.5 ש\"ח לשעה מעל גובה 23 מטר, ותוספת סיכון בעורף בסך 4 ש\"ח לשעה."}
                ],
                cbs: { mainCode: "F", mainTitle: "בינוי", subCode: "43", subTitle: "עבודות בינוי מיוחדות", microCode: "4322", microTitle: "התקנת מערכות מיזוג אוויר, אינסטלציה וחימום" }
            },
            "הובלה": {
                name: "ענף ההובלה",
                orders: "צווי 2001, 2007 ו-2018. צו 2007 ביטל סעיפי שכר של 2001. צו 2018 עדכן את מנגנון השכר המשולב והאש\"ל.",
                employerDef: "בעלי מפעלי הובלה וענפי היבוא, היצוא והמסחר בסיטונות המפעילים מערך הובלה עצמי המפורט בנספח הצו.",
                workerDef: "נהגים שתפקידם הקבוע נהיגת רכב משא להובלת מטענים שמשקלו עולה על 4 טון.",
                eligibility: "זכאות לפנסיה מיום תחילת העבודה במפעל.",
                rates: "תגמולי עובד: 5.5%, תגמולי מעסיק: 6%, פיצויים: 6% או 8.33% לקופה אישית הבאה במקום פיצויים לפי סעיף 14.",
                insuredSalary: "מחושב לפי 150% מהשכר המשולב (שכר יסוד + ותק + תוספת מקצועית קבועה).",
                exceptions: "נהגים ברכבים שמשקלם המורשה נמוך מ-4 טון, ועובדי משרד קלאסיים.",
                jurisprudence: "ע\"ע (ארצי) 78240-07-25 טמפו הובלות שותפות מוגבלת - אמיר שרם (30.04.2026): החלטה זו דנה בחברת הובלות שהיא חלק מקבוצה. בית הדין קבע כי יש לבחון את תחולת צו ההרחבה בהתאם לעיקר העיסוק של כל תאגיד בנפרד, וכי פעילותה של המעסיקה לא היוותה מרכז רווח עצמאי אלא שימשה למערך שינוע פנימי של הקבוצה, ולכן צו ההרחבה בענף ההובלה לא חל.<br> בר\"ע (ארצי) 31443-03-16 א.מ.י אוזן בנייה בע\"מ - אורן אברהם (04.04.2016): החלטה זו דנה בתחולת צו ההרחבה בענף ההובלה על חברה המפעילה מערבלי בטון. בית הדין קבע כי החברה היא מפעל הובלה שעיקר עיסוקו בהובלת בטון, וכי צו ההובלה חל עליה. ההסבה מדגישה כי הסיווג האחיד של ענפי הכלכלה הוא כלי עזר בלבד, ושינויים בו אינם משנים בהכרח את תחולת צו ההרחבה, במיוחד כאשר הפעילות הכלכלית של הובלת בטון אינה מסווגת באופן אחר בסיווג האחיד.<br> ע\"ע (ארצי) 76716-08-25 הובלות ט.ע.מ בע\"מ - אשר לוי (10.01.2026): החלטה זו דנה בחברת הובלות. בית הדין קבע כי כאשר מתעוררת שאלה של פרשנות צו הרחבה, יש לבקש את עמדת הצדדים להסכם הקיבוצי. במקרה זה, הוחזר הדיון לבית הדין האזורי לבחינה מעמיקה יותר של תחולת צו ההרחבה בענף ההובלה, במיוחד לאור טענת המעסיקה כי היא עוסקת בהובלת פסולת ולא בהובלת מטען רגילה.",
                qna: [
                    {q: "האם קרן השתלמות היא חובה בענף?", a: "כן, המעסיק מחויב להפריש 6.75% והעובד 4% (או מינימום 2.5% בכתב) לאחר תום תקופת הניסיון."},
                    {q: "מהו גובה האש\"ל המעודכן לצו 2018?", a: "האש\"ל היומי עומד על 53 ש\"ח ליום עבודה."}
                ],
                cbs: { mainCode: "H", mainTitle: "תחבורה, אחסנה ובלדרות", subCode: "49", subTitle: "תחבורה יבשתית ושינוע בצינורות", microCode: "4923", microTitle: "הובלת מטענים בדרכים" }
            },
            "חקלאות": {
                name: "חקלאות, גננות נוי ומשתלות",
                orders: "צו חקלאות כללי 2001 וצו גנני נוי ומשתלות 2001 המשלימים זה את זה.",
                employerDef: "בעלי משק חקלאי, משתלות, בתי אריזה, וחברות קבלניות המבצעות עבודות גינון ופיתוח נוי.",
                workerDef: "כל עובד מעל גיל 17, פועלים זמניים, קבועים, ועובדים בדירוג חודשי-מינהלי (מנהלי עבודה, טרקטוראים).",
                eligibility: "מיידית לקבועים ועונתיים קבועים. לזמניים - בהתאם להוראות צו פנסיה חובה כרשת ביטחון.",
                rates: "תגמולי עובד: 5.5%, תגמולי מעסיק: 6%, פיצויים: 4.5% לקבועים בקרן הביטוח.",
                insuredSalary: "שכר משולב כולל תוספת ותק ותוספת משפחה מובנית.",
                exceptions: "עובדים בעלי תנאים עדיפים בהסכמים קיבוציים מיוחדים של רשות הטבע והגנים או גופים דומים.",
                jurisprudence: "תשומת הלב כי יש 3 צווי הרחבה בענף החלקאות, יש לבדוק את ההגדרה של המעסיק והעובד ולהחיל את הוראות הצו בהתאם. אך נכון להיום, שיעור ההפרשות בהתאם לצו ההרחבה הכללי במשק מיטיב.",
                qna: [
                    {q: "האם עובדי בתי אריזה נכללים?", a: "כן, מיון ואריזת תוצרת חקלאית נכללים במפורש תחת הגדרת הענף."},
                    {q: "האם יש זכאות לביגוד?", a: "כן, זכאות לשתי חולצות, שני מכנסיים וזוג נעלי עבודה אחת לשנה."}
                ],
                cbs: { mainCode: "A", mainTitle: "חקלאות, ייעור ודיג", subCode: "01", subTitle: "גידולים חקלאיים ובעלי חיים", microCode: "0161", microTitle: "פעילויות נלוות לגידולים חקלאיים וגינון" }
            },
            "רשתות שיווק": {
                name: "רשתות שיווק מזון",
                orders: "צו הרחבה משנת 2010.",
                employerDef: "רשת המפעילה לפחות 2 חנויות לממכר מזון, או חנות מזון קמעונאית בודדת ששטח המכירה שלה מעל 500 מ\"ר.",
                workerDef: "כל עובד המועסק באופן ישיר בסניפים או במטה הרשת.",
                eligibility: "לאחר 6 חנות עבודה . אם הגיע עם פנסיה פעילה - מהיום הראשון.",
                rates: "תגמולי עובד: 5.5%, תגמולי מעסיק: 6%, פיצויים: 6% קבוע (זכאות להשלמת 28% בסיום עבודה מזכה).",
                insuredSalary: "שכר יסוד ותוספת ותק. עמלות מכירה אישיות נכללות אם הן מהוות חלק קבוע מהשכר.",
                exceptions: "מנהלי סניפים בכירים ומנהלי אזור המועסקים בחוזים אישיים הכוללים תנאי פנסיה מיטיבים.",
                jurisprudence: "תשומת הלב, כיום צו ההרחבה הכללי במשק מיטיב לעומת צו ההרחבה הענפי.",
                qna: [
                    {q: "מה קורה החל מהשנה הרביעית?", a: "העובד זכאי לתוספת ותק של 1% לשנה, דמי ביגוד שנתיים, משכורת 13 וקרן השתלמות מדורגת."},
                    {q: "מהו גובה ההפרשה לקרן השתלמות מהשנה החמישית?", a: "עולה ל-5.5% מעסיק ו-2.5% עובד."}
                ],
                cbs: { mainCode: "G", mainTitle: "מסחר סיטוני וקמעונאי ותיקון כלי רכב", subCode: "47", subTitle: "מסחר קמעונאי (למעט מסחר בכלי רכב)", microCode: "4711", microTitle: "מסחר קמעונאי בחנויות לא-מתמחות, בעיקר במזון, במשקאות ובטבק" }
            },
            "ניקיון": {
                name: "ענף הניקיון ותחזוקה",
                orders: "צו הרחבה מקיף משנת 2014 מכוח חוק הגברת האכיפה.",
                employerDef: "חברות, קבלנים ומפעלים המספקים שירותי ניקיון, תחזוקה או משרדי שירות לגופים אחרים.",
                workerDef: "עובדי ניקיון ותחזוקה בפועל המועסקים על ידי חברות אלו.",
                eligibility: "זכאות מלאה לפנסיה וקרן השתלמות מהיום הראשון לעבודה.",
                rates: "תגמולי עובד: 6%, תגמולי מעסיק: 6.5%, פיצויים: 8.33% מהיום הראשון תחת החלת סעיף 14.",
                insuredSalary: "שכר בסיס ענפי (הגבוה משכר המינימום) ותוספת ותק חודשית.",
                exceptions: "עובדי ניקיון המועסקים ישירות על ידי מעסיק פרטי בביתו (חוסים תחת הדין הכללי ולא קבלני).",
                jurisprudence: "ע\"ע (ארצי) 65753-06-20 ABDELRAHIM ISSHAG GEBRIL - מפעת 1965 (1987) בע\"מ (19.08.2021): החלטה זו דנה בחברה העוסקת בטיפול בפסולת ומיחזור. בית הדין קבע כי פעילותה אינה בתחום הניקיון, ובהתאם לסיווג האחיד מדובר במיחזור והשבה של חומרים, ולכן לא חל עליה צו ההרחבה בענף הניקיון אלא צו ההרחבה בענף אספקת כוח אדם.<br> ע\"ע (ארצי) 33745-12-21 אפיקים-תפעול בתי מלון בע\"מ - ADHANET MEHARI TESFU (02.10.2022): החלטה זו דנה בתבנית העסקה משולשת (עובדת ניקיון בבית חולים דרך חברת קבלן). בית הדין קבע כי כאשר קבלן פועל במספר ענפי שירות, כל ענף שירות בו הוא פועל נחשב למפעל בפני עצמו לצורך החלת צו ההרחבה הרלוונטי. זאת על מנת להגביר את ההגנה על זכויות העובדים ולהבטיח תחרות הוגנת בין מעסיקים.<br>בר\"ע (ארצי) 59908-05-20 BERHANE GEBRISILASI - מר פסטה זכיינות בע\"מ (01.07.2020): החלטה זו דנה בעובד ניקיון שהוצב במסעדה. בית הדין קבע כי נטל השכנוע בדבר תחולת צו הרחבה מוטל על העובד, וכי עצם העובדה שלחברה יש רישיון למתן שירותי ניקיון אינה מספיקה כדי קבוע שתחום עיסוקה העיקרי הוא ניקיון, במיוחד אם העובד עסק גם בעבודות כלליות.",
                qna: [
                    {q: "מהן ההפרשות לקרן השתלמות?", a: "7.5% מעסיק ו-2.5% עובד החל מהיום הראשון לעבודה."}
                ],
                cbs: { mainCode: "N", mainTitle: "שירותי ניהול ותמיכה", subCode: "81", subTitle: "שירותים לבניינים ולנוף", microCode: "8121", microTitle: "פעילויות ניקוי כלליות של בניינים" }
            },
            "שמירה": {
                name: "ענף השמירה והאבטחה",
                orders: "צו הרחבה משנת 2014 המבטל צווים היסטוריים.",
                employerDef: "חברות וקבלנים הרשומים והעוסקים באספקת שירותי שמירה, אבטחה וליווי.",
                workerDef: "שומרים, מאבטחים, מפקחים ואנשי צוות שטח המועסקים על ידי חברות אלו.",
                eligibility: "זכאות לפנסיה ולקרן השתלמות מהיום הראשון לעבודה.",
                rates: "תגמולי עובד: 6%, תגמולי מעסיק: 6.5%, פיצויים: 8.33% (החלה מלאה של סעיף 14).",
                insuredSalary: "שכר שעתי ענפי מוגן הכולל תוספות סיכון קבועות אם ניתנו כחלק מהגדרת המשרה.",
                exceptions: "שומרים פנימיים המועסקים ישירות על ידי מפעל תעשייתי (חוסים תחת צו התעשייה).",
                jurisprudence: "אין מידע - יתווסף בהמשך.",
                qna: [
                    {q: "מהן הפרשות קרן השתלמות בענף השמירה?", a: "7.5% מעסיק ו-2.5% עובד מהיום הראשון."}
                ],
                cbs: { mainCode: "N", mainTitle: "שירותי ניהול ותמיכה", subCode: "80", subTitle: "שירותי אבטחה וחקירות", microCode: "8010", microTitle: "פעילויות של שירותי שמירה ואבטחה פרטיים" }
            },
            "מוקד": {
                name: "ענף מוקד וסיור",
                orders: "צו הרחבה ייעודי משנת 2014 המפריד את המוקדים המבצעיים משמירה סטטית.",
                employerDef: "חברות המפעילות מוקדים סיור מבצעיים, מערכות מיגון אלקטרוניות ואזעקה.",
                workerDef: "מוקדנים, סיירים, טכנאי מיגון ומפעילי מערכות בקרה.",
                eligibility: "לאחר 3 חודשי עבודה או מהיום הראשון אם הגיע עם פנסיה פעילה.",
                rates: "תגמולי עובד: 6%, תגמולי מעסיק: 6.5%, פיצויים: 6% או 8.33% בהתאם למסלול הביטוחי.",
                insuredSalary: "שכר יסוד בתוספת מענקים רבעוניים קבועים המשולמים בגין משמרות.",
                exceptions: "אנשי מכירות שטח של מערכות אזעקה המועסקים על בסיס עמלות בלבד ללא שכר בסיס.",
                jurisprudence: " ע\"ע (ארצי) 11801-02-23 מוקד אמון-סביון (1981) בע\"מ - ראובן נח (15.05.2024): החלטה זו דנה בחברת מוקד וסיור. בית הדין קבע כי יש להבחין בין עיסוק בשמירה מסורתית לבין עיסוק בשירותי מוקד וסיור, שלהם ייחודיות המצדיקה סיווג נפרד. הסיווג האחיד של ענפי הכלכלה (2011) מבחין בין שירותי שמירה ואבטחה לבין שירותי מערכות אבטחה (הכוללים מוקדי אבטחה), וההחלטה מדגישה את השוני המהותי בין סוגי השירותים.",
                qna: [
                    {q: "האם יש תוספות מיוחדות?", a: "כן, קיימות תוספות בגין משמרות לילה וסופי שבוע מובנות בצו."}
                ],
                cbs: { mainCode: "N", mainTitle: "שירותי ניהול ותמיכה", subCode: "80", subTitle: "שירותי אבטחה וחקירות", microCode: "8020", microTitle: "פעילויות של שירותי מערכות אבטחה ומערכות בקרה" }
            },
            "מתכת": {
                name: "מתכת, חשמל ואלקטרוניקה (עד 20 עובדים)",
                orders: "צו הרחבה היסטורי ענפי.",
                employerDef: "מפעלים, בתי מלאכה המעסיקים עד 20 עובדים באחת או יותר מהעבודות הבאות מתכת, עיבוד שבבי, חריטה וכרסום, זיווד אלקטרוני, אלקטרוניקה...",
                workerDef: "כל המועסק כשכיר על ידי המפעל, שמלאו לו 18 שנים. למעט מנהל כללי, חשב, ומנהל כוח אדם.",
                eligibility: "מתחילת העבודה.",
                rates: "תגמולי עובד: 5.5%, תגמולי מעסיק: 6%, פיצויים: 6% (מותאם לרשת הביטחון המשקית).",
                insuredSalary: "השכר המבוטח יהיה השכר המשולב כהגדרתו בהסכם זה ונוסף על כך שכר עידוד (פרמיות מדודות עד 30% מהשכר).",
                exceptions: "מפעלים המעסיקים מעל 20 עובדים (אלו עוברים ישירות לתחולת צו התעשייה הכללי).",
                jurisprudence: "ענף הבנייה מול ענף המתכת, החשמל והאלקטרוניקה: במקרה של חברה העוסקת בייצור והתקנת תעלות מיזוג אוויר, נבחנה השאלה האם חל עליה צו הרחבה בענף הבנייה או בענף המתכת. סע\"ש (אזורי ת\"א) 44938-07-19 אלכסיי שניידרמן.",
                qna: [
                    {q: "האם יש זכאות למענק שנתי?", a: "כן, קיים מנגנון מענק שנתי/משכורת 13 מוקטנת בהתאם לוותק."}
                ],
                cbs: { mainCode: "C", mainTitle: "תעשייה", subCode: "25", subTitle: "ייצור מוצרי מתכת למיניהם (למעט מכונות וציוד)", microCode: "2592", microTitle: "עיבוד שבבי, חריטה, כרסום וציפוי מתכות" }
            },
            "מלונאות": {
                name: "ענף המלונאות והאירוח",
                orders: "צו הרחבה מקיף בשיתוף התאחדות המלונות בישראל.",
                employerDef: "בתי מלון, פנסיונים, בתי מרגוע ואכסניות המעניקות שירותי לינה ואירוח.",
                workerDef: "כל עובדי המלון לרבות עובדי מטבח, קבלה, משק בית ותחזוקה.",
                eligibility: "מהחודש השביעי לעבודתם או מהיום הראשון לעמית פעיל קודם.",
                rates: "תגמולי עובד: 5.5%, תגמולי מעסיק: 5%, פיצויים: 6% או 6% לפי סעיף 14.",
                insuredSalary: "משכורת כוללת שכר יסוד בצירוף תוספת ותק, תוספת משפחה, תוספת מקצועית ותוספות מיקום.",
                exceptions: "עובדי המלון כולל עובדים משרדיים.",
                jurisprudence: "ע\"ע (ארצי) 25181-03-19 מלונות הכשרת הישוב בע\"מ - שני בן עמי.",
                qna: [
                    {q: "מה קורה לגבי דמי הבראה?", a: "תעריף דמי הבראה בענף המלונאות גבוה מהתעריף הכללי במגזר הפרטי והוא צמוד למגזר הציבורי."}
                ],
                cbs: { mainCode: "I", mainTitle: "שירותי אירוח והסעדה", subCode: "55", subTitle: "שירותי אירוח", microCode: "5510", microTitle: "בתי מלון, בתי הארחה ונופש ואירוח אחר בסגנון דומה" }
            },
            "היסעים": {
                name: "ענף ההיסעים",
                orders: "צו הרחבה לנהגים בהיסעים פרטיים.",
                employerDef: "חברות פרטיות המפעילות מערך היסעים, אוטובוסים ומיניבוסים לטיולים, תלמידים ואירועים.",
                workerDef: "נהגי רכב ציבורי (אוטובוס/מיניבוס) המועסקים בחברות אלו.",
                eligibility: "לאחר 6 חודשים או מהיום הראשון אם יש פנסיה פעילה.",
                rates: "תגמולי עובד: 6%, תגמולי מעסיק: 6.5%, פיצויים: 6% (מותאם לרשת הביטחון).",
                insuredSalary: "המשכורת החודשית או מכפלת 186 שעות בשכר השעתי, בכל מקרה לא פחות מהשכר הקובע בחוק.",
                exceptions: "נהגי מוניות קטנות או הסעות עצמאיות שאינן מאורגנות כחברת היסעים.",
                jurisprudence: "אין מידע - יתווסף בהמשך.",
                qna: [
                    {q: "מהי תוספת הפיצול?", a: "פיצוי עבור שעות המתנה ארוכות בין הסעת הבוקר להסעת המנחה."}
                ],
                cbs: { mainCode: "H", mainTitle: "תחבורה, אחסנה ובלדרות", subCode: "49", subTitle: "תחבורה יבשתית ושינוע בצינורות", microCode: "4922", microTitle: "הסעת נוסעים בדרכים (אוטובוסים, היסעים וטיולים ללא קווים קבועים)" }
            },
            "הסעדה": {
                name: "שירותי הסעדה",
                orders: "צו אולמות וגני אירועים 2008 וצווי שירותי הסעדה .",
                employerDef: "חברה המספקות שירותי הסעדה למזמיני שירות.",
                workerDef: "מלצרים, טבחים, עובדי מטבח, ברמנים ואנשי תפעול אירוע.",
                eligibility: "לאחר 6 חודשי עבודה רצופים.",
                rates: "תגמולי עובד: 6%, תגמולי מעסיק: 6.5%, פיצויים: 6%.",
                insuredSalary: "שכר היסוד השעתי או החודשי.",
                exceptions: "אין .",
                jurisprudence: "אין מידע - יתווסף בהמשך.",
                qna: [
                    {q: "האם יש חובת דמי ביגוד?", a: "כן, המעסיק מחויב לספק בגדי הופעה ייצוגיים (חולצה/מכנס) או לשלם דמי ביגוד שנתיים."}
                ],
                cbs: { mainCode: "I", mainTitle: "שירותי אירוח והסעדה", subCode: "56", subTitle: "שירותי הסעדה", microCode: "5621", microTitle: "שירותי הסעדה לאירועים (קייטרינג, אולמות וגני שמחות)" }
            },
            "כוח אדם": {
                name: "אספקת שירותי כוח אדם",
                orders: "צו הרחבה משנת 2004 מכוח החוק להעסקת עובדים ע\"י קבלני כוח אדם.",
                employerDef: "חברות בעלות היתר כוח אדם העוסקות באספקה והצבה של עובדים אצל מעסיקים אחרים (משתמשים).",
                workerDef: "עובדים זמניים או קבועים המוצבים אצל המשתמש.",
                eligibility: "לאחר 9 חודשי הצבה חל עקרון השוואת התנאים המלא. לפני כן פנסיה חובה.",
                rates: "תגמולי עובד: 6%, תגמולי מעסיק: 6.5%, פיצויים: 6%.",
                insuredSalary: "נקבע לפי השכר שהיה מקבל העובד אילו היה מועסק ישירות אצל המשתמש באותו תפקיד.",
                exceptions: "קבלני שירותים מובהקים (כמו ניקיון ושמירה) שלהם יש צווי הרחבה ייחודיים.",
                jurisprudence: "כאשר עובד מועסק על ידי חברת כוח אדם, גם אם הוא מבצע עבודות ניקיון במלון או עבודות בניין, יחולו הוראות צו כוח אדם.",
                qna: [
                    {q: "מהו עקרון השוואת התנאים?", a: "העובד המוצב זכאי לכל הטבה, פנסיה, ביגוד או חופשה עודפת שחלים על עובדי המעסיק המשתמש."}
                ],
                cbs: { mainCode: "N", mainTitle: "שירותי ניהול ותמיכה", subCode: "78", subTitle: "פעילויות תעסוקה ואספקת כוח אדם", microCode: "7820", microTitle: "פעילויות של סוכנויות עבודה זמנית ואספקת כוח אדם מונחה" }
            },
            "יבוא מסחר": {
                name: "יבוא, מסחר ושירותים",
                orders: "צו הרחבה מחוזי לענפי היבוא, היצוא והמסחר בסיטונות, בשירותים ובענפים שבנספח 1 במחוזות תל-אביב והמרכז.",
                employerDef: "חברות יבוא, חברות שיווק סיטונאי, עסקי מסחר קמעונאי שאינם מזון, וחברות שירותים עסקיים באחד התחומים המנויים בנספח 1 לצו ההרחבה.",
                workerDef: "עובדי בחברות אלו.",
                eligibility: "מתחילת העבודה.",
                rates: "תגמולי עובד: 5%, תגמולי מעסיק: 6%, פיצויים: 6%.",
                insuredSalary: "שכר יסוד ועמלות מכירה קבועות. אינו כולן נסיעות ובונוסים שנתיים.",
                exceptions: "עסקים שחל עליהם צו ענפי ספציפי (כמו מוסכים, בנייה או הובלה).",
                jurisprudence: "ע\"ע (ארצי) 2580-03-11 דורון נגר - ליטוס מחשבים בע\"מ (01.03.2015) שקבע כי צו הרחבה כולל גם ענף השירותים.",
                qna: [
                    {q: "מהם התנאים המיטיבים בצו זה?", a: "תשלום דמי מחלה מלאים (100%) כבר מהיום הראשון, ימי חופשה עודפים מעבר לחוק, ודמי הבראה מוגדלים."}
                ],
                cbs: { mainCode: "G", mainTitle: "מסחר סיטוני וקמעונאי ותיקון כלי רכב", subCode: "46", subTitle: "מסחר סיטוני (למעט כלי רכב מנועיים)", microCode: "4610", microTitle: "מסחר סיטוני על פי עמלה או חוזה" }
            },
            "תעשייה": {
                name: "צו פנסיה והרחבה בתעשייה (כללי)",
                orders: "הסכם קיבוצי מורחב בין התאחדות התעשיינים להסתדרות.",
                employerDef: "מפעלים תעשייתיים, בתי חרושת וקרקעות ייצור המעסיקים מעל 20 עובדים, או חברים בהתאחדות התעשיינים.",
                workerDef: "כל עובדי הייצור, המינהל, המחסן והתחזוקה במפעלים אלו.",
                eligibility: "לאחר 6 חודשי עבודה במפעל.",
                rates: "תגמולי עובד: 6%, תגמולי מעסיק: 6.5%, פיצויים: 6% או 8.33%.",
                insuredSalary: "שכר יסוד, תוספת מחלקה ותוספות משמרות קבועות.",
                exceptions: "בתי מלאכה קטנים המעסיקים פחות מ-20 עובדים.",
                jurisprudence: "ע\"ע (ארצי) 45930-09-25 שמו הקונדיטוריה בע\"מ - נדז'דה פרקלמן (12.04.2026): החלטה זו קובעת כי צו ההרחבה בענף האפייה חל על מאפיות לאפיית לחמים ולא על מפעלים המייצרים מוצרי קונדיטוריה.  ההחלטה מדגישה כי הסיווג האחיד הוא אמצעי עזר בלבד ואינו קובע את תחולת הצו.",
                qna: [
                    {q: "האם יש זכאות לקרן השתלמות?", a: "כן, מרבית עובדי התעשייה זכאים לקרן השתלמות ענפית לאחר תקופת קציבה קבועה."}
                ],
                cbs: { mainCode: "C", mainTitle: "תעשייה", subCode: "10", subTitle: "ייצור מוצרי מזון", microCode: "1071", microTitle: "ייצור מוצרי מאפה, לחם וקונדיטוריה תעשייתית" }
            },
 "פנסיה חובה": {
                name: "צו פנסיה חובה (כל המשק) - רשת ביטחון",
                orders: "צו יסוד 2008, עדכוני 2011 ו-2016.",
                employerDef: "כל מעסיק במשק המועסק בו עובד כלשהו ושאינו כפוף לצו הרחבה ענפי מיטיב.",
                workerDef: "כל עובד בגיל זכאות שאין לו הסדר פנסיוני מיטיב אחר, למעט (1)מי שפרש מעבודתו בגיל פרישת חובה ומקבל קצבה למעט קצבאות וגמלאות מהמוסד לביטוח לאומי. 	(2) מי שטרם מלאו לו – באישה 20 שנים ובגבר 21 שנים. למען הסר ספק מובהר בזה, כי בהגיע העובד/ת לגיל האמור, יחולו עליה/ו הוראות צו זה, תוך שתילקח בחשבון, לעניין חישוב תקופת ההמתנה - עד 6 חודשים, תקופת עבודתה/ו טרם הגיע/ה לגיל האמור.",
                eligibility: "לאחר 6 חודשי עבודה או 3 חודשים רטרואקטיבית לעובד עם פוליסה פעילה.",
                rates: "תגמולי עובד: 6%, תגמולי מעסיק: 6.5%, פיצויים: 6%.",
                insuredSalary: "שכר היסוד ותוספות קבועות כקבוע בחוק פיצויי פיטורים.",
                exceptions: "מי שחל עליו הסדר פנסיוני עדיף מכוח הסכם קיבוצי או צו ענפי אחר.",
                jurisprudence: "קביעת עמלת מכירה כחלק מהשכר המבוטח לפנסיה תלויה בסיווגה כחלק משכר רגיל ולא כתוספת המותנית בתנאי. יש לבחון את מהותה של התוספת – האם שולמה עבור עבודתו הרגילה של העובד, או שמא מדובר בתוספת המותנית בתנאי או במצב. תוספת המשולמת לעובד עבור עבודה שמעבר לעבודתו הרגילה, כמרכיב עידוד או מותנית ברווחי המעסיק, אינה חלק מהשכר הקובע לפיצויי פיטורים, ולכן גם לא לפנסיה. לעומת זאת, אם העמלות משולמות כנגזרת אחוזית מכל מכירה שבוצעה, והן מהוות את עיקר השתכרותו של העובד, הן ייחשבו לחלק משכרו הרגיל. במבנה שכר שבו העמלות מהוות חלק ניכר מהשכר, יש לפרש עמימות בעניין סיווג העמלות לטובת העובד, כדי להבטיח הפרשות פנסיוניות שלא יהיו נמוכות במיוחד ביחס לשכר שקיבל העובד בפועל. \nהסרת תקרת השכר הממוצע: צו ההרחבה בדבר הגדלת ההפרשות לביטוח פנסיוני במשק משנת 2016 הסיר את התקרה שהייתה קבועה בצו ההרחבה לפנסיית חובה משנת 2008, שלפיה חובת ההפרשה חלה על השכר המשולם לעובד או השכר הממוצע במשק, לפי הנמוך. כיום, ההפרשה חלה על 'השכר הקובע' כהגדרתו בהסכם החל על העובד, ולא פחות מהשכר המבוטח המתחייב על פי צו ההרחבה לפנסיית חובה. בהיעדר התייחסות בהסכם העבודה, תחול התקרה של השכר הממוצע.\n שעות נוספות: ככלל גמול עבודה בשעות נוספות אינו חלק מהשכר המבוטח. אולם תשלום תוספת גלובלית תיחשב כחלק מהשכר המבוטח כשלא הוכח כי העובד אכן ביצע בפועל עבודה בשעות נוספות.\nעבודה במנוחה השבועית: גמול עבודה במנוחה השבועית לא נכלל בשכר המבוטח, למעט במקרים של עובד בשכר שעבודתו ביום המנוחה החליפה עבודה ביום רגיל, ובלבד מפרישים מהשכר הרגיל לא כולל תוספת הגמול",
                qna: [
                    {q: "האם יש הסדר מיוחד להפרשות לפיצויי פיטורים?", a: "בהתאם לצו ההרחבה 2016, שיעור הפרשת המעסיק לרכיב פיצויים לקרן פנסיה ו/או לקופת ביטוח ו/או לקופת גמל, יהיה בהתאם לקבוע בהסכם החל על העובד והמעסיק בלבד, שבכל מקרה לא יפחת מ-6% מהשכר הקובע. אולם היה אצל המעסיק שיעור הפרשה שונה לרכיב פיצויי פיטורים בין קופת ביטוח/קופת גמל שאינה קרן פנסיה לבין קרן פנסיה, יהיה רשאי המעסיק, לגבי עובד קיים ולגבי עובד חדש שייקלט לאחר יום כניסתו של צו זה לתוקף, להשוות את שיעור ההפרשה לרכיב פיצויי פיטורים לשיעור ההפרשה לרכיב פיצויי פיטורים הנהוג בקרן הפנסיה שלא יפחת מ-6% מהשכר הקובע כאמור, ובלבד שלא ייפגע שיעור ההפרשה לרכיב פיצויי פיטורים בגין עובד קיים; ושלא ייפגע עובד חדש הבא עם פוליסה קיימת בשיעורי ההפקדה הנקובים בפוליסה לרכיב פיצויים (ויחולו בעניינו שיעורים לרכיב פיצויים שלא יפחתו מהנקוב בפוליסה). מובהר, למען הסר ספק, כי על עובד כאמור יחול סעיף 14 ככל שזה חל על המעסיק לגבי עובדיו והוא יהיה רשאי לעבור במהלך תקופת עבודתו לכל סוג קופת גמל אחרת בלי ששיעור ההפקדה בגינו לפיצויים ייגרע.  אין באמור כדי לשנות משיעור ההפרשות לרכיב פיצויים פיטורים לגבי עובד קיים בהתאם להסכמים החלים עליו ערב כניסתו לתוקף של צו זה (לרבות לעניין הסדר סעיף 14 ככל שהיה), בלי קשר לסוג קופת הגמל בה מבוטח אותו עובד.למען הסר ספק, עובד המבוטח בקופת ביטוח/קופת גמל שאינה קרן פנסיה והמעסיק מפריש לו 8.33% לרכיב פיצויי פיטורים וחל עליו סעיף 14, ועבר לקרן פנסיה, תימשך לגביו ההפרשה בשיעור 8.33% וימשיך לחול עליו סעיף 14 על הפרשות המעסיק לרכיב פיצויי פיטורים בשיעור 8.33%.."}
                ],
                cbs: { mainCode: "U", mainTitle: "פעילויות של ארגונים וגופים חוץ-מדינתיים", subCode: "99", subTitle: "פעילויות של ארגונים חוץ-מדינתיים", microCode: "9900", microTitle: "פעילויות של גופים שאינם מסווגים בענפים מוגדרים" }
            }                  
  };

        // --- פונקציות ניווט ומעבר עמודים בטוחות ותקינות ---
        function switchPage(pageId, event) {
            if (event) {
                event.preventDefault();
            }
            
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.querySelectorAll('nav button').forEach(b => b.classList.remove('active'));
            
            const targetPage = document.getElementById('page-' + pageId);
            if (targetPage) {
                targetPage.classList.add('active');
            }
            
            const targetBtn = document.getElementById('btn-' + pageId);
            if (targetBtn) {
                targetBtn.classList.add('active');
            }

            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // --- ניהול טבלת כוח אדם דינמית ---
        function addStaffRow() {
            const tbody = document.querySelector('#staffTable tbody');
            const row = document.createElement('tr');
            row.innerHTML = `
                <td><input type="text" placeholder="תחום / מחלקה נוספת" style="width:100%"></td>
                <td><input type="number" placeholder="מספר עובדים" oninput="calcStaffPercentages()" style="width:100%"></td>
                <td><input type="number" readonly class="pct-field" style="width:100%"></td>
                <td class="no-print"><button class="btn btn-danger" onclick="deleteRow(this)">מחק</button></td>
            `;
            tbody.appendChild(row);
        }

        function deleteRow(btn) {
            const row = btn.closest('tr');
            row.remove();
            calcStaffPercentages();
        }

        function calcStaffPercentages() {
            const rows = document.querySelectorAll('#staffTable tbody tr');
            let total = 0;
            
            rows.forEach(row => {
                const numInput = row.querySelectorAll('input')[1];
                if (numInput && numInput.value) {
                    total += parseInt(numInput.value) || 0;
                }
            });

            rows.forEach(row => {
                const numInput = row.querySelectorAll('input')[1];
                const pctInput = row.querySelector('.pct-field');
                if (numInput && pctInput) {
                    const val = parseInt(numInput.value) || 0;
                    if (total > 0 && val > 0) {
                        pctInput.value = ((val / total) * 100).toFixed(1);
                    } else {
                        pctInput.value = "";
                    }
                }
            });
        }

        function handleSectorChange() {
            const sector = document.getElementById('mainSector').value;
            const desc = document.getElementById('businessDesc');
            if (sector && !desc.value) {
                desc.value = "חברה העוסקת בעיקר בתחום ה" + sector + " ומספקת שירותים רלוונטיים ללקוחותיה בישראל.";
            }
        }

        // --- מנוע ההחלטה והניתוח המשפטי המהותי ---
        function generateLegalOpinion() {
            const businessDesc = document.getElementById('businessDesc').value.trim();
            const empCountVal = document.getElementById('empCount').value.trim();
            const compName = document.getElementById('compName').value.trim() || "לא הוזן שם מעסיק";
            const mainSector = document.getElementById('mainSector').value;
            const numBranches = document.getElementById('numBranches').value.trim();
            
            const workerRole = document.getElementById('workerRole').value.trim();
            const workerSeniority = document.getElementById('workerSeniority').value.trim();
            const workerAge = document.getElementById('workerAge').value.trim();
            const pensionStatus = document.getElementById('pensionStatus').value;
            
            const salaryBase = parseFloat(document.getElementById('salaryBase').value) || 0;
            const salaryCommissions = parseFloat(document.getElementById('salaryCommissions').value) || 0;
            const salaryPremiums = parseFloat(document.getElementById('salaryPremiums').value) || 0;
            const salaryAllowances = parseFloat(document.getElementById('salaryAllowances').value) || 0;

            if (!businessDesc || !empCountVal) {
                alert("שגיאה: חובה למלא את שדות החובה המסומנים בכוכבית (*):\n1. תיאור מלא של פעילות העסק\n2. מספר עובדים כולל בעסק");
                return;
            }

            const empCount = parseInt(empCountVal) || 0;
            
            // --- אלגוריתם חילוץ והכרעת צו ההרחבה (מנגנון הכרעה משפטי וסיווג אחיד) ---
            let detectedKey = "פנסיה חובה";
            let matchReason = "לא זוהה ענף ספציפי מובהק בתיאור הפעילות. חלה רשת הביטחון הכללית של המשק.";
            let confidenceLevel = "65%";
            
            const textToAnalyze = (businessDesc + " " + mainSector + " " + workerRole).toLowerCase();

            if (textToAnalyze.includes("בנייה") || textToAnalyze.includes("תשתיות") || textToAnalyze.includes("שיפוץ") || textToAnalyze.includes("מנופאי") || textToAnalyze.includes("עגורן") || mainSector === "בנייה") {
                detectedKey = "בנייה";
                matchReason = "ניתוח מהותי של תיאור הפעילות, מחלקות כוח האדם ומאפייני האתר מצביע על זיקה ישירה לענפי הבינוי וההנדסה האזרחית. החברה מסווגת על פי הסיווג האחיד תחת סדר F (בינוי), ענף ראשי 43, המשקף ביצוע עבודות בנייה מיוחדות והתקנות באתרים. בהתאם למבחן עיקר העיסוק והפסיקה המנחה בבר\"ע 59618-01-23, נקבעה תחולת צו הבנייה.";
                confidenceLevel = "95%";
            } else if (textToAnalyze.includes("הובלה") || textToAnalyze.includes("משא") || textToAnalyze.includes("מטען") || mainSector === "הובלה") {
                detectedKey = "הובלה";
                matchReason = "החברה מפעילה מערך שינוע והובלת מטענים ברכבי משא כבדים מעל 4 טון המהווה מרכז רווח מובחן או עיסוק דומיננטי. על פי הסיווג האחיד, הפעילות משויכת לסדר H (תחבורה ואחסנה), ענף ראשי 49 (תחבורה יבשתית). הצלבת נתוני העסק וחלוקת כוח האדם עם הפסיקה בע\"ע 78240-07-25 מובילה להחלת צו ההרחבה בענף ההובלה.";
                confidenceLevel = "92%";
            } else if (textToAnalyze.includes("חקלאות") || textToAnalyze.includes("גינון") || textToAnalyze.includes("משתל") || textToAnalyze.includes("אריזה") || mainSector === "חקלאות") {
                detectedKey = "חקלאות";
                matchReason = "פעילות העסק מתמצתת בעיבוד אדמה, גידול, אריזת תוצרת חקלאית או פיתוח נוי וגינון קבלני. הסיווג האחיד משייך פעילות זו לסדר A (חקלאות, ייעור ודיג), ענף ראשי 01. שילוב תיאור הפעילות ומבחני עיקר העיסוק מחיל את צו החקלאות והגינון.";
                confidenceLevel = "88%";
            } else if (textToAnalyze.includes("ניקיון") || textToAnalyze.includes("תחזוקה") || mainSector === "ניקיון") {
                detectedKey = "ניקיון";
                matchReason = "העסק מספק שירותי ניקיון מבנים, קבלנות תחזוקה או הצבת עובדי ניקיון באתרי משתמשים. על פי הסיווג האחיד, החברה משויכת לסדר N (שירותי ניהול ותמיכה), ענף ראשי 81. בהתאם לחוק הגברת האכיפה ולמבחני תבנית ההעסקה המשולשת בע\"ע 33745-12-21, חל צו הניקיון המקיף.";
                confidenceLevel = "96%";
            } else if (textToAnalyze.includes("שמירה") || textToAnalyze.includes("אבטחה") || mainSector === "שמירה") {
                detectedKey = "שמירה";
                matchReason = "המעסיק פועל כקבלן מורשה לאספקת שירותי שמירה ואבטחה אנושית פיזית. הסיווג האחיד משייך את הפעילות לסדר N (שירותי ניהול ותמיכה), ענף ראשי 80 (שירותי אבטחה וחקירות). חלוקת כוח האדם מראה כי עיקר הפעילות מוקצה לתחום זה, ולכן חל צו השמירה הענפי.";
                confidenceLevel = "94%";
            } else if (textToAnalyze.includes("מוקד") || textToAnalyze.includes("סיור") || textToAnalyze.includes("אזעקה") || mainSector === "מוקד") {
                detectedKey = "מוקד";
                matchReason = "הפעילות מאופיינת בהפעלת מוקד בקרה מבצעי, סיור טכנולוגי חכם ומערכות התרעה אלקטרוניות. הסיווג האחיד מבחין בין שמירה מסורתית למוקדים ומסווג זאת תחת תת-ענף 8020. בהתאם לפסיקה המנחה בע\"ע 11801-02-23 המדגישה ייחודיות זו, חל צו מוקד וסיור.";
                confidenceLevel = "91%";
            } else if ((textToAnalyze.includes("רשת") || textToAnalyze.includes("סופרמרקט") || textToAnalyze.includes("מזון") || mainSector === "רשתות שיווק") && (parseInt(numBranches) >= 2 || empCount > 30)) {
                detectedKey = "רשתות שיווק";
                matchReason = "העסק עונה על תנאי הסף להגדרת רשת שיווק מזון קמעונאית בשל נפח פעילות רחב, סניפים מרובים או שטח מכירה העולה על 500 מ\"ר. על פי הסיווג האחיד, המפעל משויך לסדר G (מסחר), ענף ראשי 47, תת-ענף 4711. מבחן עיקר העיסוק מחיל את צו רשתות המזון 2010.";
                confidenceLevel = "89%";
            } else if (textToAnalyze.includes("מתכת") || textToAnalyze.includes("מסגר") || textToAnalyze.includes("אלקטרוניקה") || mainSector === "מתכת") {
                if (empCount <= 20) {
                    detectedKey = "מתכת";
                    matchReason = "העסק פועל כבית מלאכה יצרני או קבלני לעיבוד מתכת, מסגרות מבנית או ליפוף וחשמל, ומעסיק עד 20 עובדים. הסיווג האחיד משייך את היחידה לסדר C (תעשייה), ענף ראשי 25. בהתאם למגבלת נפח כוח האדם הקשיחה, חל צו המתכת ההיסטורי.";
                    confidenceLevel = "87%";
                } else {
                    detectedKey = "תעשייה";
                    matchReason = "מדובר במפעל ייצור ועיבוד מתכת או אלקטרוניקה, אולם מאחר שמצבת כוח האדם הכוללת עולה על 20 עובדים, חלה החרגה המעבירה את תחולת העסק מסדר המתכת הזעיר ישירות אל צו ההרחבה הכללי בתעשייה (סדר C, ענף ראשי 10-33).";
                    confidenceLevel = "90%";
                }
            } else if (textToAnalyze.includes("מפעל") || textToAnalyze.includes("ייצור") || textToAnalyze.includes("תעשיי") || mainSector === "תעשייה") {
                detectedKey = "תעשייה";
                matchReason = "הפעילות הדומיננטית היא ייצור פיזי תעשייתי והפיכת חומרי גלם למוצרים מוגמרים, תוך הפעלת קווי ייצור. על פי הסיווג האחיד של הלמ\"ס, המפעל משויך במובהק לסדר C (תעשייה). שילוב חלוקת העובדים ומבחני הפסיקה בע\"ע 45930-09-25 מחיל את צו התעשייה הכללי.";
                confidenceLevel = "93%";
            } else if (textToAnalyze.includes("חנות") || textToAnalyze.includes("משרד") || textToAnalyze.includes("לשכת המסחר") || textToAnalyze.includes("יבוא") || textToAnalyze.includes("שירותים") || mainSector === "יבוא מסחר") {
                detectedKey = "יבוא מסחר";
                matchReason = "החברה עוסקת במסחר סיטונאי, יבוא והפצה, או מתן שירותים עסקיים לחברות ללא ייצור פיזי. הסיווג האחיד משייך את העסק לסדר G (מסחר סיטוני), ענף ראשי 46. מכוח ההלכה המנחה בע\"ע 2580-03-11 המרחיבה את התחולה לענפי השירותים במחוזות הרלוונטיים, חל צו יבוא ומסחר.";
                confidenceLevel = "86%";
            }

            const branch = libraryData[detectedKey];

            let specialRoleWarning = "";
            if (detectedKey === "בנייה" && workerRole.includes("מנופאי")) {
                specialRoleWarning = "<strong>החרגה ייחודית:</strong> העובד מוגדר כמנופאי. חלים עליו התנאים הכספיים והבטיחותיים המועדפים של נספח מנופאים 2017 (שכר שעתי מינימלי מוגן, תוספות מאמץ וסיכון וקבינה מאובזרת במזגן).";
            } else if (detectedKey === "הובלה" && workerRole && !workerRole.includes("נהג")) {
                specialRoleWarning = "<strong>התראה משפטית:</strong> צו ההרחבה בענף ההובלה חל קטגורית על נהגים ברכבים מעל 4 טון. מכיוון שתפקיד העובד שהוזן אינו נהג מובהק, ייתכן שעל עובד מטה/משרד זה חל צו יבוא ומסחר או פנסיה חובה חלף צו ההובלה.";
            }

            let calculatedDateText = branch.eligibility;
            if (pensionStatus === "active") {
                calculatedDateText = "חל הסדר פנסיוני פעיל קודם: העובד זכאי להפרשות החל מיום העבודה הראשון (צו פנסיה חובה / הוראות פסיקה משולבות).";
            }

            let salaryBreakdownHTML = "";
            let totalInsuredSalary = 0;
            
            if (salaryBase > 0) {
                let baseFactor = 1.0;
                let calculationLog = "שכר יסוד נכלל במלואו (100%).";
                
                if (detectedKey === "הובלה") {
                    baseFactor = 1.5;
                    calculationLog = "על פי הוראות ענף ההובלה, הבסיס להפרשות מורחב ועומד על 150% משכר היסוד והרכיבים הקבועים!";
                }
                
                totalInsuredSalary += (salaryBase * baseFactor);
                
                let commissionsLog = "עמלות מכירה - לא נכללו בחישוב האוטומטי.";
                if (salaryCommissions > 0) {
                    if (detectedKey === "יבוא מסחר" || detectedKey === "רשתות שיווק") {
                        totalInsuredSalary += salaryCommissions;
                        commissionsLog = "עמלות מכירה אישיות קבועות נכללות בשכר המבוטח בענף זה על פי פסיקה ענפית.";
                    } else {
                        commissionsLog = "עמלות מכירה - בדרך כלל אינן חלק מהשכר התעריפי אלא אם הוכח שהן מהוות פיקציה להסתרת שכר יסוד.";
                    }
                }
                
                let premiumLog = "פרמיות ובונוסים מותנים - אינם נכללים בשכר הקובע לפנסיה על פי פסיקת בתי הדין לעבודה, אלא אם מדובר ברכיב גלובלי המשולם ללא תנאי.";
                if (salaryAllowances > 0) {
                    totalInsuredSalary += salaryAllowances;
                    premiumLog += " (תוספות השכר הקבועות שהוזנו בסך " + salaryAllowances + " ש\"ח נוספו לשכר המבוטח).";
                }

                salaryBreakdownHTML = `
                    <div class="table-container">
                        <table>
                            <thead>
                                <tr>
                                    <th>רכיב שכר</th>
                                    <th>סכום שהוזן</th>
                                    <th>סטטוס לצורך הפרשות</th>
                                    <th>נימוק משפטי / מקור</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>שכר יסוד / תעריפי</td>
                                    <td>${salaryBase} ש"ח</td>
                                    <td>נכלל בבסיס</td>
                                    <td>${calculationLog}</td>
                                </tr>
                                <tr>
                                    <td>עמלות מכירה</td>
                                    <td>${salaryCommissions} ש"ח</td>
                                    <td>${(detectedKey === "יבוא מסחר" || detectedKey === "רשתות שיווק") ? "נכלל" : "לא נכלל"}</td>
                                    <td>${commissionsLog}</td>
                                </tr>
                                <tr>
                                    <td>פרמיות / בונוסים ותוספות</td>
                                    <td>${salaryPremiums + salaryAllowances} ש"ח</td>
                                    <td>נכלל חלקי</td>
                                    <td>${premiumLog}</td>
                                </tr>
                                <tr style="background-color: #f1f5f9; font-weight:700;">
                                    <td>סך שכר מבוטח משוער</td>
                                    <td colspan="3">${totalInsuredSalary.toFixed(2)} ש"ח</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                `;
            } else {
                salaryBreakdownHTML = `<p><em>לא הוזנו נתוני שכר בסיס בסימולטור. מוצגות הוראות והגדרות הצו הכלליות בלבד ללא חישוב סכומים חודשיים.</em></p>`;
            }

            let alertBoxHTML = "";
            if (detectedKey === "חקלאות" || detectedKey === "הובלה" || detectedKey === "רשתות שיווק") {
                alertBoxHTML = `
                    <div class="alert-warning-box">
                        <strong>לתשומת לבך (הסדר מיטיב משקי):</strong> החל מהמועד הקבוע בצו ההרחבה לפנסיה חובה במשק (עדכוני 2016), העובד עשוי להיות זכאי להסדר מיטיב יותר ברכיבי אחוזי ההפרשה מזה הקבוע במקור בצו הענפי ההיסטורי. המעסיק מחויב להפריש לפחות את רצפת אחוזי המשק (6.5% מעסיק, 6% עובד) במידה והבסיס הענפי הישן נמוך מהם, אלא אם בסיס השכר הרחב (כמו 150% בהובלה) מפצה על כך מהותית.
                    </div>
                `;
            }

            let partialDataHeader = "";
            if (!workerRole || !workerSeniority || !workerAge || salaryBase === 0) {
                partialDataHeader = `
                    <div class="alert-info-box" style="border-right-color: var(--accent-color); background-color: #fef3c7; color: #92400e;">
                        <strong>לתשומת לב המשתמש:</strong> חוות הדעת הופקה על בסיס הנתונים החלקיים שהוזנו בסימולטור, וייתכן שנדרש מידע נוסף לצורך קביעה סופית ומדויקת לחלוטין.
                    </div>
                `;
            }

            // חילוץ נתוני סיווג למ"ס בטוחים
            const cbsData = branch.cbs || { mainCode: "U", mainTitle: "לא מסווג", subCode: "00", subTitle: "ללא", microCode: "0000", microTitle: "רשת ביטחון כללית" };

            // פירוק אחוזי ההפרשות בצורה בטוחה ומבוקרת למניעת קריסות קונסול
            let rate1 = "6%", rate2 = "6.5%", rate3 = "6%";
            if (branch.rates && branch.rates.includes(',')) {
                const parts = branch.rates.split(',');
                if (parts[0]) rate1 = parts[0].replace('תגמולי עובד:', '').trim();
                if (parts[1]) rate2 = parts[1].replace('תגמולי מעסיק:', '').trim();
                if (parts[2]) rate3 = parts[2].replace('פיצויים:', '').trim();
            } else if (branch.rates) {
                rate2 = branch.rates;
            }

            const opinionHTML = `
                ${partialDataHeader}
                <div class="report-section">
                    <h2>חוות דעת משפטית - תחולת צו הרחבה וזכויות פנסיוניות</h2>
                    <p style="font-size:12px; color:var(--text-muted);">הופק בתאריך: 11 ביוני 2026 | מזהה פנימי: משרד העבודה - יחסי עבודה</p>
                </div>

                <div class="report-section" style="background: #fdfefe; border: 1px dashed var(--border-color); padding: 15px; border-radius: 6px; margin-bottom: 20px;">
                    <h3 style="color: var(--primary-color); border-bottom: 1px solid var(--border-color); padding-bottom: 4px;">ניתוח מובנה על פי הסיווג האחיד של ענפי הכלכלה (הלמ"ס)</h3>
                    <div class="report-grid" style="background-color: #f8fafc; margin-top: 10px;">
                        <div class="report-item"><span class="lbl">ענף ראשי (סדר)</span><span class="val"><strong>[${cbsData.mainCode}]</strong> ${cbsData.mainTitle}</span></div>
                        <div class="report-item"><span class="lbl">ענף משנה (קוד)</span><span class="val"><strong>[${cbsData.subCode}]</strong> ${cbsData.subTitle}</span></div>
                        <div class="report-item"><span class="lbl">תת-ענף (מיקרו)</span><span class="val"><strong>[${cbsData.microCode}]</strong> ${cbsData.microTitle}</span></div>
                        <div class="report-item"><span class="lbl">רמת ודאות הסיווג</span><span class="val" style="color: var(--success-color); font-weight: 700;">${confidenceLevel}</span></div>
                    </div>
                    <p style="font-size:13px; margin-top:10px; color: var(--text-main); line-height: 1.4;">
                        <strong>הסבר הולכת הסיווג לתחולת הצו:</strong> שיוך פעילות העסק לקוד הלמ"ס הבוחן את תיאור המוצרים והשירותים המרכזיים, בשילוב חלוקת כוח האדם הפנימית (מבחן עיקר העיסוק), יוצר זיקה משפטית ישירה והרמונית אל תוך הגדרות ה\"מעסיק\" וה\"מפעל\" המפורטות בלשון צו ההרחבה ופסיקת בתי הדין לעבודה.
                    </p>
                </div>

                <div class="report-section">
                    <h3>1. פרטי הישות המשפטית והמעסיק שנבחנו</h3>
                    <div class="report-grid">
                        <div class="report-item"><span class="lbl">שם המעסיק</span><span class="val">${compName}</span></div>
                        <div class="report-item"><span class="lbl">מספר עובדים כולל</span><span class="val">${empCount}</span></div>
                        <div class="report-item"><span class="lbl">תחום מועדף שנבחר</span><span class="val">${mainSector || "לא נבחר - זיהוי אוטומטי"}</span></div>
                        <div class="report-item"><span class="lbl">מספר סניפים</span><span class="val">${numBranches || "לא הוזן מידע"}</span></div>
                    </div>
                    <p style="margin-top:10px; font-size:14px;"><strong>תיאור הפעילות המערכתית:</strong> ${businessDesc}</p>
                </div>

                <div class="report-section">
                    <h3>2. צו ההרחבה החל והנמקה משפטית מהותית</h3>
                    <p style="font-size:16px; font-weight:700; color:var(--primary-color); margin-bottom:8px;">
                        צו חל משוער: ${branch.name}
                    </p>
                    <p><strong>נימוק ומנגנון הכרעה:</strong> ${matchReason}</p>
                    <p style="margin-top:8px; font-size:14px; background:#f1f5f9; padding:10px; border-radius:4px;">
                        <strong>מקור משפטי / פסיקה מנחה:</strong> ${branch.jurisprudence}<br>
                        <em>הערה: קביעת התחולה מבוססת על בחינה אובייקטיבית של עיקר פעילותו של המעסיק וחלוקת כוח האדם הכללית, ולא על פי כותרת החוזה.</em>
                    </p>
                    ${specialRoleWarning ? `<p style="margin-top:10px;">${specialRoleWarning}</p>` : ''}
                </div>

                <div class="report-section">
                    <h3>3. תנאי זכאות ומועד תחילת ההפרשות לפנסיה</h3>
                    <div class="report-grid">
                        <div class="report-item"><span class="lbl">תנאי זכאות כלליים</span><span class="val">${branch.eligibility}</span></div>
                        <div class="report-item"><span class="lbl">מועד הפעלה בפועל</span><span class="val">${calculatedDateText}</span></div>
                    </div>
                </div>

                <div class="report-section">
                    <h3>4. שיעורי הפרשות וחלוקת אחוזים לקופות</h3>
                    <div class="report-grid" style="background-color: #ecfdf5;">
                        <div class="report-item"><span class="lbl">תגמולי עובד (ניכוי)</span><span class="val" style="color:var(--primary-color); font-weight:700;">${rate1}</span></div>
                        <div class="report-item"><span class="lbl">תגמולי מעסיק (הפרשה)</span><span class="val" style="color:var(--primary-color); font-weight:700;">${rate2}</span></div>
                        <div class="report-item"><span class="lbl">פיצויי פיטורים (מעסיק)</span><span class="val" style="color:var(--primary-color); font-weight:700;">${rate3}</span></div>
                    </div>
                    ${alertBoxHTML}
                </div>

                <div class="report-section">
                    <h3>5. הגדרת השכר המבוטח ורכיביו</h3>
                    <p style="font-size:14px; margin-bottom:8px;"><strong>כללי הענף:</strong> ${branch.insuredSalary}</p>
                    ${salaryBreakdownHTML}
                </div>

                <div class="report-section" style="background-color: #fafafa; padding:15px; border-radius:6px;">
                    <h3>6. הערות משפטיות והוראות פיקוח חיוניות</h3>
                    <p style="font-size:13px; color:var(--text-main);">
                        * חובת המעסיק לערוך שימוע כדין ולבדוק אקטיבית קיום קופות קודמות מול העובד.<br>
                        * זכויות סוציאליות רבות כגון חופשה, מחלה והבראה מבוססות בענף זה על <strong>ותק ענפי מצטבר</strong> ולא רק ותק אצל המעסיק הנוכחי. נטל ההוכחה של הוותק הענפי מוטל על העובד באמצעות מסמכים רשמיים.<br>
                        * במידה ומתעוררת אי-ודאות עובדתית לגבי עיקר העיסוק (לדוגמה עסק מעורב של מסחר וייצור שבו כוח האדם מחולק שווה בשווה), נדרשת בחינה משפטית פרטנית משלימה של היחידה ליחסי עבודה.
                    </p>
                </div>
            `;

            document.getElementById('opinion-container').innerHTML = opinionHTML;
            switchPage('output');
        }

        // --- פונקציות עזר: העתקת טקסט ---
        function copyOpinion() {
            const container = document.getElementById('opinion-container');
            const text = container.innerText;
            navigator.clipboard.writeText(text).then(() => {
                alert("חוות הדעת הועתקה בהצלחה לקליפבורד לשילוב במסמכים חיצוניים!");
            }).catch(err => {
                alert("שגיאה בהעתקת הטקסט: " + err);
            });
        }

        // --- ניהול וטעינת ספריית צווי ההרחבה המובנית ---
        function initLibrary() {
            const menu = document.getElementById('libMenu');
            menu.innerHTML = "";
            
            Object.keys(libraryData).forEach((key, index) => {
                const btn = document.createElement('button');
                btn.className = 'lib-menu-item';
                if (index === 0) btn.classList.add('active');
                btn.innerText = libraryData[key].name;
                btn.onclick = (e) => showLibDetails(key, e);
                btn.setAttribute('data-key', key);
                menu.appendChild(btn);
            });

            showLibDetails(Object.keys(libraryData)[0]);
        }

        function showLibDetails(key, event) {
            if (event && event.currentTarget) {
                document.querySelectorAll('.lib-menu-item').forEach(b => b.classList.remove('active'));
                event.currentTarget.classList.add('active');
            }

            const data = libraryData[key];
            const content = document.getElementById('libContent');

            let qnaHTML = "";
            if (data.qna && data.qna.length > 0) {
                qnaHTML = `<h3>שאלות ותשובות נפוצות בענף</h3>`;
                data.qna.forEach(item => {
                    qnaHTML += `
                        <p style="font-weight:600; color:var(--primary-color); margin-top:8px;">שאלת מוקד: ${item.q}</p>
                        <p style="margin-bottom:8px; font-size:14px; background:#f8fafc; padding:8px; border-right:3px solid var(--success-color);">תשובה והנחיה: ${item.a}</p>
                    `;
                });
            }

            const cbsInfo = data.cbs ? `<div style="margin-bottom:12px; background: #f8fafc; padding: 8px; border-left: 3px solid var(--secondary-color);"><strong>מפתח סיווג אחיד למ"ס:</strong> סדר ${data.cbs.mainCode} (${data.cbs.mainTitle}) | קוד ענף ${data.cbs.subCode} | תת-ענף ${data.cbs.microCode} (${data.cbs.microTitle})</div>` : "";

            content.innerHTML = `
                <h2>${data.name}</h2>
                <p style="font-size:13px; color:var(--text-muted); margin-bottom:15px;"><strong>צווים היסטוריים ועדכונים:</strong> ${data.orders}</p>
                ${cbsInfo}
                <div style="margin-bottom:12px;"><strong>הגדרת מעסיק בתקנות:</strong><br><span style="font-size:14px; color:#334155;">${data.employerDef}</span></div>
                <div style="margin-bottom:12px;"><strong>הגדרת עובד מזכה:</strong><br><span style="font-size:14px; color:#334155;">${data.workerDef}</span></div>
                <div style="margin-bottom:12px;"><strong>מועד תחילת זכאות לפנסיה:</strong><br><span style="font-size:14px; color:#334155;">${data.eligibility}</span></div>
                <div style="margin-bottom:12px;"><strong>שיעורי הפרשות:</strong><br><span style="font-size:14px; color:#334155; font-weight:600;">${data.rates}</span></div>
                <div style="margin-bottom:12px;"><strong>הגדרת השכר המבוטח ורכיבים:</strong><br><span style="font-size:14px; color:#334155;">${data.insuredSalary}</span></div>
                <div style="margin-bottom:12px;"><strong>חריגים וסייגים בולטים:</strong><br><span style="font-size:14px; color:#334155;">${data.exceptions}</span></div>
                <div style="margin-bottom:15px; background-color:#eff6ff; padding:10px; border-radius:4px;">
                    <strong>פסיקה מרכזית ומנחה:</strong><br><span style="font-size:13px; color:var(--primary-color); font-weight:500;">${data.jurisprudence}</span>
                </div>
                ${qnaHTML}
            `;
        }

        function filterLibrary() {
            try {
                const query = document.getElementById('libSearch').value.toLowerCase();
                const items = document.querySelectorAll('.lib-menu-item');
                
                items.forEach(item => {
                    const text = item.innerText.toLowerCase();
                    const key = item.getAttribute('data-key');
                    
                    let fullDataText = "";
                    try {
                        fullDataText = JSON.stringify(libraryData[key]).toLowerCase();
                    } catch(jsonErr) {
                        fullDataText = text; 
                    }
                    
                    if (text.includes(query) || fullDataText.includes(query)) {
                        item.style.display = 'block';
                    } else {
                        item.style.display = 'none';
                    }
                });
            } catch(e) {
                console.error("שגיאה במערך החיפוש והסינון: ", e);
            }
        }

        // טעינה ראשונית של המערכת
        window.onload = function() {
            try {
                initLibrary();
                console.log("מפתח ענפים נטען בהצלחה:", Object.keys(libraryData));
                console.log("מערכת מומחה משפטית - נטענה בהצלחה ללא שגיאות קונסול.");
            } catch(loadErr) {
                console.error("שגיאה קריטית בטעינת האפליקציה: ", loadErr);
            }
        };
    </script>
</body>
</html>
