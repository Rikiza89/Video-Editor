<!DOCTYPE html>
<html lang="ja" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>インタラクティブ・レポート：ビデオ編集ツールUIコンセプト</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;500;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Warm Neutrals -->
    <!-- Application Structure Plan: 単一カラムのテーマ別SPA。デモリンク付きのヒーローセクションから始まり、インタラクティブな技術スタックカードを備えた概要、視覚的な「使い方」ガイド、探索用のUIレイアウトのインタラクティブ図、そして貢献セクションが続きます。この直線的で物語的な構造は、その単純さと明瞭さから選択され、ユーザーをプロジェクトのコンセプトから貢献までのストーリーを通して導き、元の静的なREADMEよりも魅力的なものにします。 -->
    <!-- Visualization & Content Choices: README '技術スタック' -> Goal: 整理 -> Presentation: インタラクティブなHTML/CSSカード -> Interaction: クリックで情報を表示 -> Justification: 静的なリストよりも魅力的。| README 'UIコンセプト' (暗示的) -> Goal: 説明/デモ -> Presentation: インタラクティブなUIブロック図 (HTML/CSS) -> Interaction: パネルをクリックして別のテキストエリアにその機能を表示 -> Justification: プロジェクトの核となるコンセプトを視覚的に説明し、抽象的なUIレイアウトを具体的で探索可能なものにします。 -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Noto Sans JP', sans-serif;
            background-color: #fdfdfc;
            color: #383838;
        }
        .nav-link {
            transition: color 0.3s ease-in-out, border-color 0.3s ease-in-out;
            border-bottom: 2px solid transparent;
        }
        .nav-link:hover, .nav-link.active {
            color: #2563eb;
            border-bottom-color: #2563eb;
        }
        .tech-card {
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
            cursor: pointer;
        }
        .tech-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
        }
        .step-item {
            border-left: 3px solid #d1d5db;
        }
        .ui-diagram-panel {
            transition: background-color 0.3s ease, transform 0.2s ease;
            cursor: pointer;
        }
        .ui-diagram-panel:hover {
            transform: scale(1.02);
        }
        .ui-diagram-panel.active {
            background-color: #3b82f6 !important;
            color: white;
        }
        .section-fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }
        .section-fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800">

    <header class="bg-white/80 backdrop-blur-lg sticky top-0 z-50 shadow-sm">
        <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
            <div class="text-xl font-bold text-blue-600">
                UIコンセプト探求
            </div>
            <div class="hidden md:flex space-x-8">
                <a href="#overview" class="nav-link pb-1">概要</a>
                <a href="#how-to-use" class="nav-link pb-1">使い方</a>
                <a href="#layout" class="nav-link pb-1">レイアウト</a>
                <a href="#contribute" class="nav-link pb-1">貢献</a>
            </div>
        </nav>
    </header>

    <main class="container mx-auto px-6 py-8 md:py-16">

        <section id="hero" class="text-center py-16 md:py-24 section-fade-in">
            <h1 class="text-4xl md:text-6xl font-extrabold tracking-tight mb-4">シンプルなビデオ編集ツール</h1>
            <p class="text-lg md:text-xl text-slate-600 max-w-3xl mx-auto">
                レスポンシブなレイアウトとサイズ変更可能なパネルを備えた、モダンなビデオ編集UIのコンセプトを探るインタラクティブ・レポート。
            </p>
            <div class="mt-8">
                <a href="#" class="bg-blue-600 text-white font-bold py-3 px-8 rounded-full hover:bg-blue-700 transition-colors duration-300 text-lg">
                    デモを見る (準備中)
                </a>
            </div>
        </section>

        <div class="space-y-24 md:space-y-32">

            <section id="overview" class="section-fade-in">
                <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold">プロジェクト概要</h2>
                    <p class="mt-4 text-lg text-slate-600">フロントエンド技術のみで構築された、UIのプロトタイプです。</p>
                </div>
                <div class="grid md:grid-cols-2 gap-8 items-center">
                    <div class="text-slate-700 leading-relaxed space-y-4">
                        <p>このプロジェクトは、ビデオ編集アプリケーションのユーザーインターフェース（UI）コンセプトを実証するために作成されました。実際のビデオ処理のようなバックエンド機能は含まれていませんが、Webベース編集ツールの設計とインタラクションのプロトタイプとして機能します。</p>
                        <p>現代的なダークテーマのデザインと、ユーザーが自由にパネルサイズを変更できる柔軟なレイアウトが特徴です。</p>
                    </div>
                    <div>
                        <h3 class="text-xl font-bold mb-4 text-center">主な技術スタック</h3>
                        <div id="tech-stack-container" class="grid grid-cols-2 gap-4">
                            <div class="tech-card bg-white p-4 rounded-lg shadow-md border border-slate-200" data-tech="html">
                                <h4 class="font-bold text-center">HTML5</h4>
                            </div>
                            <div class="tech-card bg-white p-4 rounded-lg shadow-md border border-slate-200" data-tech="tailwind">
                                <h4 class="font-bold text-center">Tailwind CSS</h4>
                            </div>
                            <div class="tech-card bg-white p-4 rounded-lg shadow-md border border-slate-200" data-tech="jquery">
                                <h4 class="font-bold text-center">jQuery / UI</h4>
                            </div>
                             <div class="tech-card bg-white p-4 rounded-lg shadow-md border border-slate-200" data-tech="japanese">
                                <h4 class="font-bold text-center">日本語対応</h4>
                            </div>
                        </div>
                        <div id="tech-description" class="mt-4 p-4 bg-blue-50 text-blue-800 rounded-lg min-h-[80px] flex items-center justify-center text-center">
                            <p>技術カードをクリックして詳細を表示します。</p>
                        </div>
                    </div>
                </div>
            </section>

            <section id="how-to-use" class="section-fade-in">
                <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold">使い方</h2>
                    <p class="mt-4 text-lg text-slate-600">ビルド不要で、簡単に試すことができます。</p>
                </div>
                <div class="max-w-2xl mx-auto space-y-8">
                    <div class="step-item relative pl-8 pb-8">
                        <div class="absolute top-1 left-[-11px] h-5 w-5 bg-blue-500 rounded-full border-4 border-slate-50"></div>
                        <h3 class="text-xl font-bold">1. ファイル取得</h3>
                        <p class="text-slate-700 mt-1">`video_editor_responsive_jp.html` ファイルをダウンロードまたはクローンします。</p>
                    </div>
                    <div class="step-item relative pl-8 pb-8">
                        <div class="absolute top-1 left-[-11px] h-5 w-5 bg-blue-500 rounded-full border-4 border-slate-50"></div>
                        <h3 class="text-xl font-bold">2. ブラウザで開く</h3>
                        <p class="text-slate-700 mt-1">お好みのWebブラウザでダウンロードしたファイルを開きます。</p>
                    </div>
                    <div class="step-item relative pl-8">
                        <div class="absolute top-1 left-[-11px] h-5 w-5 bg-blue-500 rounded-full border-4 border-slate-50"></div>
                        <h3 class="text-xl font-bold">3. 動作を試す</h3>
                        <p class="text-slate-700 mt-1">ウィンドウサイズを変更したり、パネル境界線をドラッグして、UIの柔軟性を確認します。</p>
                    </div>
                </div>
            </section>

            <section id="layout" class="section-fade-in">
                 <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold">インタラクティブ・レイアウト</h2>
                    <p class="mt-4 text-lg text-slate-600">UIの主要コンポーネントをクリックして、その役割を確認しましょう。</p>
                </div>
                <div class="bg-white p-6 rounded-lg shadow-lg border border-slate-200">
                    <div class="w-full h-[300px] md:h-[400px] bg-slate-200 rounded-t-md p-4 flex gap-4" id="ui-diagram">
                        <div id="panel-left" class="ui-diagram-panel bg-slate-400 rounded flex items-center justify-center text-white font-bold w-1/4">左パネル</div>
                        <div id="panel-center" class="ui-diagram-panel bg-slate-500 rounded flex items-center justify-center text-white font-bold w-1/2">中央パネル</div>
                        <div id="panel-right" class="ui-diagram-panel bg-slate-400 rounded flex items-center justify-center text-white font-bold w-1/4">右パネル</div>
                    </div>
                     <div id="layout-description" class="mt-4 p-4 bg-slate-100 text-slate-800 rounded-b-md min-h-[100px] flex flex-col items-center justify-center text-center">
                        <h4 class="font-bold text-lg">パネルを選択</h4>
                        <p>上の図の各パネルをクリックすると、その機能説明がここに表示されます。</p>
                    </div>
                </div>
            </section>

            <section id="contribute" class="text-center section-fade-in">
                 <h2 class="text-3xl md:text-4xl font-bold">貢献</h2>
                 <p class="mt-4 text-lg text-slate-600 max-w-2xl mx-auto">バグ報告や改善提案を歓迎します。IssueやPull Requestを通じてお気軽にご協力ください。</p>
                 <div class="mt-8 flex justify-center gap-4">
                     <a href="#" class="bg-slate-800 text-white font-bold py-3 px-6 rounded-full hover:bg-slate-900 transition-colors duration-300">
                         GitHub Issues
                     </a>
                     <a href="#" class="border-2 border-slate-800 text-slate-800 font-bold py-3 px-6 rounded-full hover:bg-slate-800 hover:text-white transition-colors duration-300">
                         Pull Requests
                     </a>
                 </div>
            </section>
        </div>
    </main>

    <footer class="bg-white mt-16 md:mt-24 border-t">
        <div class="container mx-auto px-6 py-8 text-center text-slate-500">
            <p>&copy; 2024 Rikiza89. All Rights Reserved.</p>
            <p class="text-sm mt-2">このインタラクティブ・レポートは、提供されたREADME.mdを基に生成されました。</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {

            const techData = {
                html: {
                    title: "HTML5",
                    description: "コンテンツの構造とセマンティクスを定義するために使用されます。"
                },
                tailwind: {
                    title: "Tailwind CSS",
                    description: "レスポンシブデザインと迅速なスタイリングのためのユーティリティファーストCSSフレームワークです。"
                },
                jquery: {
                    title: "jQuery / jQuery UI",
                    description: "パネルのサイズ変更（Resizable）などのインタラクティブな機能を実装するために使用されます。"
                },
                japanese: {
                    title: "日本語対応",
                    description: "インターフェースのテキストはすべて日本語で記述されており、日本のユーザーを対象としています。"
                }
            };
            
            const techContainer = document.getElementById('tech-stack-container');
            const techDescriptionEl = document.getElementById('tech-description');
            
            techContainer.addEventListener('click', (e) => {
                const card = e.target.closest('.tech-card');
                if (card) {
                    const techKey = card.dataset.tech;
                    const data = techData[techKey];
                    techDescriptionEl.innerHTML = `<p>${data.description}</p>`;
                }
            });

            const layoutData = {
                'panel-left': {
                    title: '左パネル: アセット領域',
                    description: '通常、ビデオクリップ、画像、音声ファイルなどのメディアアセットや、エフェクト、トランジションの一覧が表示されます。'
                },
                'panel-center': {
                    title: '中央パネル: プレビュー & タイムライン',
                    description: 'ビデオのプレビュー画面と、クリップを編集・配置するためのタイムラインで構成される主要な作業領域です。'
                },
                'panel-right': {
                    title: '右パネル: プロパティ & 詳細',
                    description: '選択されたクリップやエフェクトの色調整、サイズ、位置などの詳細なプロパティを編集するためのパネルです。'
                }
            };

            const uiDiagram = document.getElementById('ui-diagram');
            const layoutDescriptionEl = document.getElementById('layout-description');
            const panels = uiDiagram.querySelectorAll('.ui-diagram-panel');

            uiDiagram.addEventListener('click', (e) => {
                const panel = e.target.closest('.ui-diagram-panel');
                if (panel) {
                    const panelId = panel.id;
                    const data = layoutData[panelId];

                    panels.forEach(p => p.classList.remove('active'));
                    panel.classList.add('active');
                    
                    layoutDescriptionEl.innerHTML = `
                        <h4 class="font-bold text-lg mb-2">${data.title}</h4>
                        <p>${data.description}</p>
                    `;
                }
            });
            
            const sections = document.querySelectorAll('.section-fade-in');
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                    }
                });
            }, {
                threshold: 0.1
            });
            sections.forEach(section => {
                observer.observe(section);
            });
            
            const navLinks = document.querySelectorAll('a.nav-link');
            const navObserver = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const id = entry.target.getAttribute('id');
                        document.querySelector(`a.nav-link[href="#${id}"]`)?.classList.add('active');
                    } else {
                         const id = entry.target.getAttribute('id');
                        document.querySelector(`a.nav-link[href="#${id}"]`)?.classList.remove('active');
                    }
                });
            }, { rootMargin: "-50% 0px -50% 0px" });

            document.querySelectorAll('section[id]').forEach(section => {
                navObserver.observe(section);
            });
        });
    </script>
</body>
</html>
