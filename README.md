# helloworld
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>圣力律师事务所 - 专业法律服务</title>
    <style>
        /* 基础重置与全局样式 */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { 
            font-family: "微软雅黑", sans-serif; 
            line-height: 1.6; 
            color: #333; 
            background: #f8f9fa url('https://s41.ax1x.com/2025/12/23/pZ85XqS.jpg') no-repeat center center fixed; 
            background-size: cover; 
        }
        .container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }
        
        /* 导航栏 */
        header { 
            background: rgba(44, 62, 80, 0.9); 
            position: fixed; 
            width: 100%; 
            top: 0; 
            z-index: 100; 
        }
        nav { display: flex; justify-content: space-between; align-items: center; padding: 15px 0; }
        .logo { color: #fff; font-size: 1.5rem; font-weight: bold; }
        .nav-links { display: flex; list-style: none; gap: 30px; }
        .nav-links a { color: #ecf0f1; text-decoration: none; transition: color 0.3s; }
        .nav-links a:hover { color: #3498db; }
        .menu-btn { display: none; color: #fff; font-size: 1.2rem; cursor: pointer; }
        
        /* 英雄区域 */
        .hero { 
            height: 100vh; 
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), 
                        url('https://via.placeholder.com/1920x1080?text=律所办公环境') center/cover; 
            display: flex; 
            align-items: center; 
            justify-content: center; 
            text-align: center; 
            color: #fff; 
            margin-top: 60px; 
        }
        .hero h1 { font-size: 3rem; margin-bottom: 20px; text-shadow: 0 2px 4px rgba(0,0,0,0.5); }
        .hero p { font-size: 1.2rem; max-width: 800px; margin: 0 auto 30px; text-shadow: 0 1px 2px rgba(0,0,0,0.5); }
        
        /* 通用区块样式 */
        section { 
            padding: 80px 0; 
            background: rgba(255,255,255,0.9); 
            margin: 20px 0; 
            border-radius: 10px; 
        }
        .section-title { text-align: center; font-size: 2rem; margin-bottom: 50px; color: #2c3e50; }
        
        /* 业务领域 */
        .services { background: rgba(255,255,255,0.95); }
        .service-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px; }
        .service-card { 
            background: #f8f9fa; 
            padding: 30px; 
            border-radius: 10px; 
            box-shadow: 0 2px 10px rgba(0,0,0,0.1); 
            transition: transform 0.3s; 
        }
        .service-card:hover { transform: translateY(-5px); }
        .service-card h3 { color: #3498db; margin-bottom: 15px; }
        
        /* 团队介绍（核心优化：确保图片显示） */
        .team { background: rgba(248,249,250,0.95); }
        .team-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 30px; }
        .team-member { text-align: center; }
        /* 灰色圆圈容器：圆形+灰色背景+固定尺寸 */
        .member-photo { 
            width: 150px; 
            height: 150px; 
            border-radius: 50%; /* 圆形 */
            background: #ddd; /* 灰色背景（加载失败时显示） */
            margin: 0 auto 20px; /* 居中+下间距 */
            overflow: hidden; /* 隐藏超出部分 */
            display: flex; 
            align-items: center; 
            justify-content: center; 
        }
        /* 图片样式：填满圆圈+保持比例 */
        .member-photo img { 
            width: 100%; 
            height: 100%; 
            object-fit: cover; /* 裁剪多余部分，不变形 */
        }
        
        /* 联系我们 */
        .contact { 
            background: rgba(44, 62, 80, 0.9); 
            color: #fff; 
        }
        .contact-form { max-width: 600px; margin: 0 auto; }
        .form-group { margin-bottom: 20px; }
        .form-group label { display: block; margin-bottom: 5px; }
        .form-group input, .form-group textarea { 
            width: 100%; 
            padding: 10px; 
            border: none; 
            border-radius: 5px; 
            background: rgba(255,255,255,0.9); 
        }
        .btn { 
            background: #3498db; 
            color: #fff; 
            padding: 12px 30px; 
            border: none; 
            border-radius: 5px; 
            cursor: pointer; 
            transition: background 0.3s; 
        }
        .btn:hover { background: #2980b9; }
        
        /* 页脚 */
        footer { 
            background: rgba(26, 37, 47, 0.9); 
            color: #ecf0f1; 
            text-align: center; 
            padding: 30px 0; 
        }
        
        /* 响应式设计 */
        @media (max-width: 768px) {
            .menu-btn { display: block; }
            .nav-links { 
                position: absolute; 
                top: 60px; 
                left: 0; 
                right: 0; 
                background: rgba(44, 62, 80, 0.95); 
                flex-direction: column; 
                align-items: center; 
                padding: 20px 0; 
                gap: 15px; 
                display: none; 
            }
            .nav-links.active { display: flex; }
            .hero h1 { font-size: 2rem; }
            .hero p { font-size: 1rem; }
        }
    </style>
</head>
<body>
    <!-- 导航栏 -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">圣力律师事务所</div>
                <div class="menu-btn" onclick="toggleMenu()">☰</div>
                <ul class="nav-links" id="navLinks">
                    <li><a href=" ">首页</a ></li>
                    <li><a href="#about">关于我们</a ></li>
                    <li><a href="#services">业务领域</a ></li>
                    <li><a href="#team">专业团队</a ></li>
                    <li><a href="#contact">联系我们</a ></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- 英雄区域 -->
    <section class="hero" id="home">
        <div class="container">
            <h1>专业法律护航，守护您的权益</h1>
            <p>圣力律师事务所专注商事诉讼、知识产权、婚姻家庭等领域，26年行业经验，为数千客户提供优质法律服务</p >
            <button class="btn" onclick="scrollToSection('contact')">免费咨询</button>
        </div>
    </section>

    <!-- 关于我们 -->
    <section id="about">
        <div class="container">
            <h2 class="section-title">关于我们</h2>
            <p style="max-width: 800px; margin: 0 auto; text-align: center;">圣力律师事务所是一家立足于本土化服务和国际化服务相结合的法律专业服务机构，于1999年2月10日经吉林市司法局批准成立，由资深律师团队创立，秉持"诚信、专业、高效"理念，致力于为客户提供全方位法律解决方案，经历二十余年的锐意进取，承办了大量公司运营、房地产开发建设、国际经贸、外商投资、知识产权等方面的法律事务，树立了良好的业绩和声誉，秉承诚信、勤勉、高效、卓越的职业理念，提供专业、优质的法律服务，使客户在接受本所的法律服务中感到安全和满意。 我们确信，建立在共同努力、相互信任基础上的合作，一定会取得客户满意的成效。</p >
            <p style="max-width: 800px; margin: 0 auto; text-align: center;">我们期待和客户共同迎接新的挑战和更大的成功。</p >
        </div>
    </section>


    <!-- 业务领域（保持不变） -->
    <section class="services" id="services">
        <div class="container">
            <h2 class="section-title">核心业务</h2>
            <div class="service-grid">
                <div class="service-card">
                    <h3>商事诉讼</h3>
                    <p>涵盖合同纠纷、股权争议、破产清算等，擅长复杂商事案件代理，曾为客户挽回经济损失超2亿元。</p >
                </div>
                <div class="service-card">
                    <h3>知识产权</h3>
                    <p>专利/商标侵权维权、著作权保护、商业秘密管理，代理多起知名企业知识产权案胜诉。</p >
                </div>
                <div class="service-card">
                    <h3>婚姻家庭</h3>
                    <p>离婚财产分割、子女抚养权纠纷、遗产继承，注重情感疏导与法律权益平衡。</p >
                </div>
                <div class="service-card">
                    <h3>刑事辩护</h3>
                    <p>经济犯罪、职务犯罪辩护，坚持罪刑法定原则，维护当事人合法权益。</p >
                </div>
                <div class="service-card">
                    <h3>房地产纠纷</h3>
                    <p>专业解决房地产纠纷，拆解矛盾维护客户合法权益。</p >
                </div>
                <div class="service-card">
                    <h3>企业法律顾问</h3>
                    <p>提供企业全流程风控与合规支持，护航经营稳定。</p >
                </div>
                <div class="service-card">
                    <h3>建设工程纠纷</h3>
                    <p>擅长建设工程履约争议处理，保障项目有序推进。</p >
                </div>
                <div class="service-card">
                    <h3>各类商事/劳动仲裁</h3>
                    <p>代理各类仲裁案件，高效推动争议解决、定分止争。</p >
                </div>
            </div>
        </div>
    </section>
    <!-- 主任律师（已删除灰色圆圈和图片） -->
    <section class="team" id="team">
        <div class="container">
            <h2 class="section-title">专业团队</h2>
            <div class="team-grid">
                <div class="team-member">
                    <!-- 已删除：灰色圆圈容器（.member-photo）和图片（img标签） -->
                    <h3>郭双权</h3>
                    <p>微信：gsqls123456 联系电话：1364477593</p >
                    <p>20余年商事诉讼经验，擅长复杂合同纠纷处理。</p >
                </div>
            </div>
        </div>
    </section>

    <!-- 联系我们 -->
    <section class="contact" id="contact">
        <div class="container">
            <h2 class="section-title">联系我们</h2>
            <div class="contact-form">
                <div class="form-group">
                    <label>姓名</label>
                    <input type="text" placeholder="请输入您的姓名">
                </div>
                <div class="form-group">
                    <label>电话</label>
                    <input type="tel" placeholder="请输入联系电话">
                </div>
                <div class="form-group">
                    <label>咨询事项</label>
                    <textarea rows="5" placeholder="请简要描述您的需求"></textarea>
                </div>
                <button class="btn">提交咨询</button>
            </div>
            <div style="margin-top: 40px; text-align: center;">
                <p>地址：吉林省吉林市昌邑区昌邑法院西侧</p >
                <p>电话：13644477593</p >
            </div>
        </div>
    </section>

    <!-- 页脚 -->
    <footer>
        <div class="container">
            <p>© 2025 圣力律师事务所 版权所有</p >
            <p>免责声明：本网站内容仅供参考，不构成法律意见</p >
        </div>
    </footer>

    <script>
        // 导航菜单折叠（移动端）
        function toggleMenu() {
            const navLinks = document.getElementById('navLinks');
            navLinks.classList.toggle('active');
        }

        // 平滑滚动到指定区块
        function scrollToSection(sectionId) {
            const section = document.getElementById(sectionId);
            window.scrollTo({ top: section.offsetTop - 60, behavior: 'smooth' });
        }

        // 监听导航链接点击（关闭移动端菜单）
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                document.getElementById('navLinks').classList.remove('active');
            });
        });
    </script>
</body>
</html>
