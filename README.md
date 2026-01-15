<！doctype html>
<超文本标记语言朗="zh-CN">
<头>
    <元字符集="UTF-8">
    <元姓名="视口" 内容="宽度=设备宽度，初始比例=1.0">
    <标题>响应式菜单演示</标题>
    <风格>
        * {
            边缘: 0;
            填充: 0;
            箱体尺寸: 边框框;
            字体系列: '宋体', 无衬线;
        }
        /* 导航栏样式 */
.navbar{
            背景色：#2c3e50；
            宽度: 100%;
            位置: 粘性的;
            顶端: 0;
            Z指数: 100;
        }
.nav-容器{
            最大宽度: 1200PX;
            边缘: 0 自动;
            显示: 弯曲;
            justify-content: 间距;
            对齐项目: 中心;
            填充: 0 20PX;
        }
.logo{
            颜色: 白色的;
            字体大小: 1.5REM;
            字体粗细: 大胆的;
            填充: 15PX 0;
            文字装饰: 没有一个;
        }
        /* 桌面端菜单 */
.nav-menu{
            显示: 弯曲;
            列表式: 没有一个;
        }
.nav-item{
            位置: 相对的;
        }
.nav-link{
            颜色: 白色的;
            文字装饰: 没有一个;
            填充: 18PX 20PX;
            显示: 块;
            过渡: 背景色 0.3s;
        }
.nav-link：盘旋 {
            背景色：#34495e；
        }
        /* 下拉子菜单 */
.dropdown{
            位置: 绝对的;
            顶端: 100%;
            左: 0;
            background-color: #34495e;
            list-style: none;
            width: 200px;
            display: none;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }
        .dropdown-item .nav-link {
            padding: 12px 20px;
            border-bottom: 1px solid #45637d;
        }
        .dropdown-item:last-child .nav-link {
            border-bottom: none;
        }
        .nav-item:hover .dropdown {
            display: block;
        }
        /* 移动端菜单按钮 */
        .menu-toggle {
            display: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }
        /* 内容区域 */
        .content {
            max-width: 1200px;
            margin: 40px auto;
            padding: 0 20px;
        }
        .content h1 {
            color: #2c3e50;
            margin-bottom: 20px;
        }
        .content p {
            line-height: 1.6;
            color: #34495e;
            margin-bottom: 20px;
        }
        /* 响应式适配（移动端） */
        @media (max-width: 768px) {
            .nav-menu {
                position: fixed;
                top: 60px;
                left: -100%;
                flex-direction: column;
                background-color: #2c3e50;
                width: 100%;
                height: calc(100vh - 60px);
                transition: 0.3s;
            }
            .nav-menu.active {
                left: 0;
                overflow-y: auto;
            }
            .dropdown {
                position: static;
                width: 100%;
                background-color: #45637d;
            }
            .menu-toggle {
                display: block;
            }
        }
    </style>
</head>
<body>
    <!-- 导航栏 -->
    <nav class="navbar">
        <div class="nav-container">
            <a href="#" class="logo">菜单演示</a>
            <div class="menu-toggle" id="menuToggle">☰</div>
            <ul class="nav-menu" id="navMenu">
                <li class="nav-item">
                    <a href="#" class="nav-link">首页</a>
                </li>
                <li class="nav-item">
                    <a href="#" class="nav-link">关于我们</a>
                </li>
                <li class="nav-item">
                    <a href="#" class="nav-link">服务 ▾</a>
                    <ul class="dropdown">
                        <li class="dropdown-item"><a href="#" class="nav-link">网站开发</a></li>
                        <li class="dropdown-item"><a href="#" class="nav-link">设计服务</a></li>
                        <li class="dropdown-item"><a href="#" class="nav-link">维护支持</a></li>
                    </ul>
                </li>
                <li class="nav-item">
                    <a href="#" class="nav-link">案例 ▾</a>
                    <ul class="dropdown">
                        <li class="dropdown-item"><a href="#" class="nav-link">企业官网</a></li>
                        <li class="dropdown-item"><a href="#" class="nav-link">电商平台</a></li>
                        <li class="dropdown-item"><a href="#" class="nav-link">移动端应用</a></li>
                    </ul>
                </li>
                <li class="nav-item">
                    <a href="#" class="nav-link">联系我们</a>
                </li>
            </ul>
        </div>
    </nav>

    <!-- 内容区域 -->
    <div class="content">
        <h1>响应式菜单功能演示</h1>
        <p>这是一个带下拉子菜单的响应式导航栏，支持：</p>
        <p>1. 桌面端：hover显示下拉子菜单，导航栏固定在顶部</p>
        <p>2. 移动端：点击汉堡菜单按钮展开/收起导航，适配手机屏幕</p>
        <p>3. 平滑过渡动画，hover效果，清晰的层级结构</p>
        <p>可根据需求修改菜单内容、颜色、样式，直接嵌入你的项目中使用～</p>
    </div>

    <script>
        // 移动端菜单切换
        const menuToggle = document.getElementById('menuToggle');
        const navMenu = document.getElementById('navMenu');

    menuToggle.addEventListener('click'，()=>{
    navMenu.classList.toggle('active')；
    //切换汉堡菜单图标(☰ ↔ ✕)
    menuToggle.textContent=navMenu.classList.Contains('active')？'✕'：'☰'；
        });

    // 点击导航链接后收起移动端菜单
    常量navlinks=document.querySelectorAll('.nav-link')；
    navLinks.forEach(link=>{
    link.addEventListener('click'，()=>{
    if(window.innerWidth<=768){
    navMenu.classList.remove('active')；
    menuToggle.textContent='☰'；
                }
            });
        });

    // 窗口大小变化时重置菜单状态
    window.addEventListener('resize'，()=>{
    if(window.innerWidth>768){
    navMenu.classList.remove('active')；
    menuToggle.textContent='☰'；
            }
        });
    </script>
</身体>
</超文本标记语言>

