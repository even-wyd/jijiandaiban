[极简待办 (1).html](https://github.com/user-attachments/files/28041182/1.html)


<头>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover, user-scalable=no">
    <title>极简待办 · 轻量小程序</title>
    <样式>

            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            字体：system-ui, -apple-system, 'Segoe UI', 'Roboto', 'Helvetica Neue', 无衬线;
            背景: 线性渐变(145度, #f5f7fe 0%, #eef2fa 100%);
            最小高度：100vh；
            填充: 20px 16px;
            过渡：背景 0.25秒 ease，颜色 0.2秒 ease;
        }

        /* 深色模式变量 */
        body.dark {
            背景: 线性渐变(145度, #121826 0%, #1a1f2c 100%);
        }

        /* 主卡片 */
        .app-card {
            最大宽度：550像素；
            margin: 0 auto;
            背景: rgba(255, 255, 255, 0.92);
            背景过滤器：模糊(2px);
            border-radius: 40px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.08), 0 5px 12px rgba(0, 0, 0, 0.05);
            溢出: 隐藏;
            过渡: 背景 0.25秒 ease, 盒阴影 0.3秒 ease;
        }

        body.dark .app-card {
            背景: rgba(30, 35, 48, 0.96);
            box-shadow: 0 20px 35px rgba(0, 0, 0, 0.3);
        }

        /* 头部区域 */
        .header {
            内边距：28px 24px 16px 24px;
            border-bottom: 1px solid rgba(0, 0, 0, 0.06);
            显示: 弹性布局;
            文本对齐方式：空间之间；
            对齐项目: 基线;
            弹性布局：换行；
            缝隙：12px;
        }

        body.dark .header {
            边框底部颜色: rgba(255, 255, 255, 0.08);
        }

        标题部分 h1 {</b>
            字体大小：1.85rem;
            字体粗细：600；
            背景: 线性渐变(135度, #1e2b6e, #2b3b8c);
            背景剪辑：文本；
            -webkit背景剪辑：文本；
            颜色：透明；
            字母间距: -0.3px;
        }

        body.dark .title-section h1 {
            背景: 线性渐变(135度, #b9d0ff, #7c9eff);
            背景剪辑：文本；
            -webkit背景剪辑：文本；
            颜色：透明；
        }

        .sub {
            字体大小：0.8rem;
            颜色: #5b6e8c;
            上边距：6px;
        }

        body dark .sub {
            颜色: #9aa9c1;
        }

        /* 深色模式切换按钮 */
        .theme-toggle {
            background: rgba(110, 120, 150, 0.15);
            border: none;
            width: 44px;
            height: 44px;
            border-radius: 30px;
            font-size: 1.6rem;
            cursor: pointer;
            backdrop-filter: blur(4px);
            transition: all 0.2s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #2c3e66;
        }

        body.dark .theme-toggle {
            background: rgba(200, 210, 255, 0.2);
            color: #ffde9c;
        }

        .theme-toggle:hover {
            transform: scale(0.96);
            background: rgba(90, 100, 140, 0.25);
        }

        /* 输入区域 */
        .input-area {
            padding: 20px 24px 12px 24px;
            display: flex;
            gap: 12px;
            align-items: center;
        }

        .task-input {
            flex: 1;
            padding: 14px 18px;
            border: 1.5px solid #e2e8f0;
            border-radius: 60px;
            font-size: 1rem;
            background: white;
            transition: all 0.2s;
            outline: none;
            font-weight: 500;
            color: #1f2a44;
        }

        body.dark .task-input {
            background: #252b3d;
            border-color: #3d445b;
            color: #eceff8;
        }

        .task-input:focus {
            border-color: #5f7ef2;
            box-shadow: 0 0 0 3px rgba(95, 126, 242, 0.2);
        }

        .add-btn {
            background: #2b3b8c;
            border: none;
            width: 52px;
            height: 52px;
            border-radius: 52px;
            color: white;
            font-size: 1.7rem;
            cursor: pointer;
            transition: 0.2s;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 10px rgba(43, 59, 140, 0.3);
        }

        body.dark .add-btn {
            background: #4c6ef5;
            box-shadow: 0 4px 12px rgba(76, 110, 245, 0.3);
        }

        .add-btn:active {
            transform: scale(0.94);
        }

        /* 任务列表容器 */
        .list-container {
            padding: 8px 16px 8px 20px;
            max-height: 460px;
            overflow-y: auto;
        }

        .task-list {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        /* 单个任务卡片 */
        .task-item {
            background: white;
            border-radius: 28px;
            padding: 8px 16px 8px 12px;
            display: flex;
            align-items: center;
            gap: 12px;
            transition: all 0.2s;
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.04);
            border: 1px solid rgba(0, 0, 0, 0.03);
        }

        body.dark .task-item {
            background: #262e42;
            border-color: rgba(255, 255, 255, 0.05);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }

        .task-check {
            width: 24px;
            height: 24px;
            cursor: pointer;
            accent-color: #4c6ef5;
            flex-shrink: 0;
        }

        .task-text {
            flex: 1;
            font-size: 1rem;
            font-weight: 500;
            color: #1e2a47;
            word-break: break-word;
            padding: 10px 0;
            transition: 0.15s;
        }

        body.dark .task-text {
            color: #eef2ff;
        }

        .completed-text {
            text-decoration: line-through;
            opacity: 0.65;
            color: #6c7a9e;
        }

        .task-actions {
            display: flex;
            gap: 8px;
            flex-shrink: 0;
        }

        .icon-btn {
            background: transparent;
            border: none;
            font-size: 1.3rem;
            cursor: pointer;
            padding: 8px 6px;
            border-radius: 30px;
            transition: 0.15s;
            width: 38px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            color: #6c7a9e;
        }

        .icon-btn:hover {
            background: rgba(0, 0, 0, 0.05);
            transform: scale(0.95);
        }

        body.dark .icon-btn {
            color: #b1bedb;
        }

        body.dark .icon-btn:hover {
            background: rgba(255, 255, 255, 0.1);
        }

        .edit-btn:active, .delete-btn:active {
            transform: scale(0.92);
        }

        /* 底部统计栏 */
        .footer-stats {
            padding: 18px 24px 22px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-top: 1px solid rgba(0, 0, 0, 0.06);
            flex-wrap: wrap;
            gap: 12px;
        }

        body.dark .footer-stats {
            border-top-color: rgba(255, 255, 255, 0.08);
        }

        .remaining {
            font-size: 0.85rem;
            font-weight: 500;
            background: rgba(100, 120, 200, 0.12);
            padding: 6px 14px;
            border-radius: 40px;
            color: #2c3e66;
        }

        body.dark .remaining {
            background: rgba(100, 120, 210, 0.2);
            color: #ccdcff;
        }

        .clear-btn {
            background: rgba(220, 80, 100, 0.1);
            border: none;
            padding: 8px 18px;
            border-radius: 40px;
            font-size: 0.85rem;
            font-weight: 500;
            color: #d15b6e;
            cursor: pointer;
            transition: 0.2s;
            backdrop-filter: blur(2px);
        }

        body.dark .clear-btn {
            background: rgba(230, 100, 120, 0.2);
            color: #ffa1b3;
        }

        .clear-btn:active {
            transform: scale(0.96);
            background: rgba(220, 80, 100, 0.25);
        }

        .empty-placeholder {
            text-align: center;
            padding: 48px 20px;
            color: #8f9bb3;
            font-size: 0.95rem;
            letter-spacing: 0.3px;
        }

        body.dark .empty-placeholder {
            color: #7b89a6;
        }

        /* 滚动条美观 */
        .list-container::-webkit-scrollbar {
            width: 5px;
        }

        .list-container::-webkit-scrollbar-track {
            background: #e9eef4;
            border-radius: 10px;
        }

        body.dark .list-container::-webkit-scrollbar-track {
            background: #2a3042;
        }

        .list-container::-webkit-scrollbar-thumb {
            background: #b9c4da;
            border-radius: 10px;
        }

        body.dark .list-container::-webkit-scrollbar-thumb {
            background: #4a5572;
        }
    </style>
</head>
<body>

<div class="app-card">
    <div class="header">
        <div class="title-section">
            <h1>✨ 极简待办</h1>
            <div class="sub">轻量 · 专注 · 随手记</div>
        </div>
        <button class="theme-toggle" id="themeToggleBtn" aria-label="深色模式">🌙</button>
    </div>

    <div class="input-area">
        <input type="text" class="task-input" id="taskInput" placeholder="写一个任务，比如「学习小程序开发」" autocomplete="off">
        <button class="add-btn" id="addTaskBtn">+</button>
    </div>

    <div class="list-container">
        <ul class="task-list" id="taskList">
            <!-- 动态渲染列表 -->
            <li class="empty-placeholder">✨ 暂无任务，添加一条开始吧</li>
        </ul>
    </div>

    <div class="footer-stats">
        <span class="remaining" id="remainingCount">剩余 0 项</span>
        <button class="clear-btn" id="clearCompletedBtn">🗑 清除已完成</button>
    </div>
</div>

<script>
    // ---------- 数据模型 ----------
    let tasks = [];     // 每个任务结构: { id, text, completed }

    // 本地存储 KEY
    const STORAGE_KEY = 'minimal_todo_app';
    
    // DOM 元素
    const taskListEl = document.getElementById('taskList');
    const taskInput = document.getElementById('taskInput');
    const addBtn = document.getElementById('addTaskBtn');
    const remainingSpan = document.getElementById('remainingCount');
    const clearCompletedBtn = document.getElementById('clearCompletedBtn');
    const themeToggle = document.getElementById('themeToggleBtn');

    // ---------- 辅助函数 ----------
    // 保存到 localStorage
    function saveToLocalStorage() {
        localStorage.setItem(STORAGE_KEY, JSON.stringify(tasks));
    }

    // 加载初始数据 (本地存储 或 默认示例)
    function loadInitialTasks() {
        const stored = localStorage.getItem(STORAGE_KEY);
        if (stored) {
            try {
                const parsed = JSON.parse(stored);
                if (Array.isArray(parsed)) {
                    tasks = parsed;
                    return;
                }
            } catch(e) { console.warn(e); }
        }
        // 默认示例数据：优雅又不打扰
        tasks = [
            { id: Date.now() + 101, text: '📖 阅读《JavaScript高级程序设计》', completed: false },
            { id: Date.now() + 102, text: '🎨 体验深色模式切换', completed: false },
            { id: Date.now() + 103, text: '✅ 点击复选框完成任务', completed: true },
            { id: Date.now() + 104, text: '✏️ 点击 ✏️ 编辑任务内容', completed: false },
        ];
        saveToLocalStorage();
    }

    // 更新底部剩余未完成任务数量
    function updateRemainingCount() {
        const remaining = tasks.filter(t => !t.completed).length;
        remainingSpan.innerText = `剩余 ${remaining} 项`;
    }

    // 渲染任务列表（完全根据tasks数组绘制，事件使用委托机制）
    function renderTasks() {
        if (!taskListEl) return;
        
        if (tasks.length === 0) {
            taskListEl.innerHTML = `<li class="empty-placeholder">🧘 清空啦，给自己加个新任务吧</li>`;
            updateRemainingCount();
            return;
        }

        // 生成所有任务 HTML (使用 data-id 存储原始ID)
        let html = '';
        for (const task of tasks) {
            const checkedAttr = task.completed ? 'checked' : '';
            const textClass = task.completed ? 'task-text completed-text' : 'task-text';
            // 转义文本，防止XSS (text 可能包含特殊字符)
            const safeText = escapeHtml(task.text);
            html += `
                <li class="task-item" data-task-id="${task.id}">
                    <input type="checkbox" class="task-check" ${checkedAttr} data-id="${task.id}">
                    <span class="${textClass}">${safeText}</span>
                    <div class="task-actions">
                        <button class="icon-btn edit-btn" data-action="edit" data-id="${task.id}" title="编辑">✏️</button>
                        <button class="icon-btn delete-btn" data-action="delete" data-id="${task.id}" title="删除">🗑️</button>
                    </div>
                </li>
            `;
        }
        taskListEl.innerHTML = html;
        updateRemainingCount();
    }

    // 简单转义 HTML 特殊字符 (防止注入)
    function escapeHtml(str) {
        if (!str) return '';
        return str.replace(/[&<>]/g, function(m) {
            if (m === '&') return '&amp;';
            if (m === '<') return '&lt;';
            if (m === '>') return '&gt;';
            return m;
        }).replace(/[\uD800-\uDBFF][\uDC00-\uDFFF]/g, function(c) {
            return c;
        });
    }

    // 核心: 添加新任务
    function addTask() {
        let text = taskInput.value.trim();
        if (text === "") {
            // 轻提示风格：简单不打扰的反馈
            const alertMsg = document.createElement('div');
            alertMsg.textContent = '📝 内容不能为空，写点什么吧';
            alertMsg.style.position = 'fixed';
            alertMsg.style.bottom = '20px';
            alertMsg.style.left = '50%';
            alertMsg.style.transform = 'translateX(-50%)';
            alertMsg.style.backgroundColor = '#ffecba';
            alertMsg.style.color = '#8a6e2f';
            alertMsg.style.padding = '8px 22px';
            alertMsg.style.borderRadius = '40px';
            alertMsg.style.fontSize = '0.85rem';
            alertMsg.style.zIndex = '999';
            alertMsg.style.fontWeight = '500';
            alertMsg.style.boxShadow = '0 4px 12px rgba(0,0,0,0.1)';
            document.body.appendChild(alertMsg);
            setTimeout(() => { alertMsg.remove(); }, 1800);
            return;
        }
        
        // 避免过长文本撑爆
        if (text.length > 120) {
            text = text.slice(0, 117) + '...';
        }
        
        const newTask = {
            id: Date.now(),
            text: text,
            completed: false
        };
        tasks.push(newTask);
        saveToLocalStorage();
        renderTasks();
        taskInput.value = '';    // 清空输入框
        taskInput.focus();
        // 添加轻柔动画反馈 (滚动到新任务位置)
        setTimeout(() => {
            const lastItem = document.querySelector('.task-item:last-child');
            if (lastItem) lastItem.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
        }, 80);
    }

    // 切换任务完成状态
    function toggleComplete(taskId) {
        const task = tasks.find(t => t.id == taskId);
        if (task) {
            task.completed = !task.completed;
            saveToLocalStorage();
            renderTasks();
        }
    }

    // 删除任务
    function deleteTask(taskId) {
        tasks = tasks.filter(t => t.id != taskId);
        saveToLocalStorage();
        renderTasks();
    }

    // 编辑任务文本 (使用prompt修改)
    function editTask(taskId) {
        const task = tasks.find(t => t.id == taskId);
        if (!task) return;
        let newText = prompt('✏️ 编辑任务内容', task.text);
        if (newText !== null) {
            newText = newText.trim();
            if (newText === "") {
                // 不修改为空，简单提示
                const tip = document.createElement('div');
                tip.textContent = '⚠️ 任务内容不能为空，未做修改';
                tip.style.cssText = 'position:fixed; bottom:20px; left:50%; transform:translateX(-50%); background:#ffd9d9; color:#b13b3b; padding:6px 20px; border-radius:40px; font-size:0.8rem; z-index:999;';
                document.body.appendChild(tip);
                setTimeout(() => tip.remove(), 1500);
                return;
            }
            if (newText.length > 120) newText = newText.slice(0, 117) + '...';
            task.text = newText;
            saveToLocalStorage();
            renderTasks();
        }
    }

    // 清除所有已完成任务
    function clearCompleted() {
        const hasCompleted = tasks.some(t => t.completed === true);
        if (!hasCompleted) {
            // 无已完成任务时轻提示
            const msg = document.createElement('div');
            msg.textContent = '✨ 暂无已完成的任务，好干净~';
            msg.style.cssText = 'position:fixed; bottom:20px; left:50%; transform:translateX(-50%); background:#d9f0e3; color:#2b6e4e; padding:6px 20px; border-radius:40px; font-size:0.8rem; z-index:999;';
            document.body.appendChild(msg);
            setTimeout(() => msg.remove(), 1500);
            return;
        }
        // 二次确认（优雅体验）
        const confirmClear = confirm('🗑️ 确定要清空所有已完成的任务吗？');
        if (confirmClear) {
            tasks = tasks.filter(t => !t.completed);
            saveToLocalStorage();
            renderTasks();
        }
    }

    // ---------- 事件委托 (处理复选框/编辑/删除) ----------
    function handleTaskListClick(e) {
        let target = e.target;
        // 向上查找可能触发元素（防止点击内部span）
        const isCheckbox = target.classList && target.classList.contains('task-check');
        const isEditBtn = target.classList && target.classList.contains('edit-btn');
        const isDeleteBtn = target.classList && target.classList.contains('delete-btn');
        
        if (isCheckbox) {
            const taskId = target.getAttribute('data-id');
            if (taskId) toggleComplete(taskId);
            e.stopPropagation();
        } 
        else if (isEditBtn) {
            const taskId = target.getAttribute('data-id');
            if (taskId) editTask(taskId);
            e.stopPropagation();
        }
        else if (isDeleteBtn) {
            const taskId = target.getAttribute('data-id');
            if (taskId) deleteTask(taskId);
            e.stopPropagation();
        }
        // 额外处理如果点击了图标里的文字或者svg，但button包裹, 确保获取正确
        else {
            // 可能会点到子元素 (比如✏️文本) 向上找到button
            let parentBtn = target.closest('.edit-btn');
            if (parentBtn && parentBtn.classList.contains('edit-btn')) {
                const taskId = parentBtn.getAttribute('data-id');
                if (taskId) editTask(taskId);
                e.stopPropagation();
                return;
            }
            parentBtn = target.closest('.delete-btn');
            if (parentBtn && parentBtn.classList.contains('delete-btn')) {
                const taskId = parentBtn.getAttribute('data-id');
                if (taskId) deleteTask(taskId);
                e.stopPropagation();
                return;
            }
            // 处理复选框可能点到label区域但直接上是checkbox 已经拦截, 忽略额外
        }
    }

    // 针对 change 事件 (某些浏览器点击复选框可能会触发change, 为了防止重复, 但我们的click已经处理了change, 为了避免重复保存, 直接禁用change额外逻辑)
    function handleTaskListChange(e) {
        // 由于我们已经通过click处理checkbox切换, 这里不再重复处理, 避免二次渲染
        // 但为了防止潜在的冒泡混乱, 只做拦截无操作
        if (e.target && e.target.classList && e.target.classList.contains('task-check')) {
            // 实际toggle逻辑已在click执行, 避免重复渲染, 只需要阻止默认动作混乱
            e.preventDefault();
        }
    }

    // 回车添加任务
    function onInputKeyPress(e) {
        if (e.key === 'Enter') {
            e.preventDefault();
            addTask();
        }
    }

    // ---------- 深色模式 (本地存储偏好) ----------
    function initTheme() {
        const savedTheme = localStorage.getItem('todo_theme');
        const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
        const isDark = savedTheme === 'dark' || (savedTheme === null && prefersDark);
        if (isDark) {
            document.body.classList.add('dark');
            themeToggle.textContent = '☀️';
        } else {
            document.body.classList.remove('dark');
            themeToggle.textContent = '🌙';
        }
    }
    
    function toggleTheme() {
        if (document.body.classList.contains('dark')) {
            document.body.classList.remove('dark');
            localStorage.setItem('todo_theme', 'light');
            themeToggle.textContent = '🌙';
        } else {
            document.body.classList.add('dark');
            localStorage.setItem('todo_theme', 'dark');
            themeToggle.textContent = '☀️';
        }
    }

    // ---------- 全局初始化 ----------
    function init() {
        loadInitialTasks();      // 加载存储或默认数据
        renderTasks();           // 首次渲染
        initTheme();            // 应用深色/浅色模式
        
        // 事件绑定
        if (taskListEl) {
            taskListEl.addEventListener('click', handleTaskListClick);
            taskListEl.addEventListener('change', handleTaskListChange);
        }
        addBtn.addEventListener('click', addTask);
        taskInput.addEventListener('keypress', onInputKeyPress);
        clearCompletedBtn.addEventListener('click', clearCompleted);
        themeToggle.addEventListener('click', toggleTheme);
    }
    
    // 启动一切
    init();
</script>
</body>
</html>
