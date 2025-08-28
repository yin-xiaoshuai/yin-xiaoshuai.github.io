<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>七夕情人节 - 浪漫相会</title>
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Font Awesome -->
  <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
  <!-- 自定义配置 -->
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            primary: '#FF69B4', // 粉色主色调
            secondary: '#DDA0DD', // 淡紫色
            accent: '#FFD700', // 金色
            light: '#FFF0F5', // 浅粉色
            dark: '#8B008B' // 深紫色
          },
          fontFamily: {
            romantic: ['"Noto Serif SC"', 'serif']
          }
        }
      }
    }
  </script>
  <style type="text/tailwindcss">
    @layer utilities {
      .text-shadow {
        text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
      }
      .text-shadow-lg {
        text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.5);
      }
      .animate-float {
        animation: float 6s ease-in-out infinite;
      }
      .animate-twinkle {
        animation: twinkle 3s ease-in-out infinite;
      }
      .animate-fade-in {
        animation: fadeIn 1s ease-in forwards;
      }
      .bg-gradient-romantic {
        background: linear-gradient(135deg, #FFF0F5 0%, #FFB6C1 50%, #FF69B4 100%);
      }
    }

    @keyframes float {
      0% { transform: translateY(0px); }
      50% { transform: translateY(-20px); }
      100% { transform: translateY(0px); }
    }
    
    @keyframes twinkle {
      0%, 100% { opacity: 0.5; }
      50% { opacity: 1; }
    }
    
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    /* 导入中文字体 */
    @import url('https://fonts.googleapis.com/css2?family=Noto+Serif+SC:wght@400;700&display=swap');
  </style>
</head>
<body class="bg-light font-romantic text-gray-800 overflow-x-hidden">
  <!-- 星星背景 -->
  <div id="stars" class="fixed top-0 left-0 w-full h-full pointer-events-none z-0"></div>
  
  <!-- 导航栏 -->
  <nav class="bg-primary/90 text-white shadow-lg fixed w-full z-50 transition-all duration-300" id="navbar">
    <div class="container mx-auto px-4 py-3 flex justify-between items-center">
      <div class="flex items-center space-x-2">
        <i class="fa fa-heart text-accent text-2xl animate-pulse"></i>
        <span class="text-xl font-bold">七夕浪漫夜</span>
      </div>
      <div class="hidden md:flex space-x-8">
        <a href="#story" class="hover:text-accent transition-colors duration-300">七夕故事</a>
        <a href="#customs" class="hover:text-accent transition-colors duration-300">传统习俗</a>
        <a href="#poems" class="hover:text-accent transition-colors duration-300">爱情诗句</a>
        <a href="#wishes" class="hover:text-accent transition-colors duration-300">爱的寄语</a>
      </div>
      <button class="md:hidden text-white focus:outline-none" id="menuToggle">
        <i class="fa fa-bars text-xl"></i>
      </button>
    </div>
    <!-- 移动端菜单 -->
    <div class="md:hidden hidden bg-primary/95 absolute w-full" id="mobileMenu">
      <div class="container mx-auto px-4 py-2 flex flex-col space-y-3">
        <a href="#story" class="py-2 hover:text-accent transition-colors duration-300">七夕故事</a>
        <a href="#customs" class="py-2 hover:text-accent transition-colors duration-300">传统习俗</a>
        <a href="#poems" class="py-2 hover:text-accent transition-colors duration-300">爱情诗句</a>
        <a href="#wishes" class="py-2 hover:text-accent transition-colors duration-300">爱的寄语</a>
      </div>
    </div>
  </nav>

  <!-- 英雄区域 -->
  <header class="relative min-h-screen flex items-center justify-center overflow-hidden pt-16">
    <div class="absolute inset-0 z-0">
      <img src="https://picsum.photos/id/1068/1920/1080" alt="星空下的浪漫场景" class="w-full h-full object-cover opacity-50">
      <div class="absolute inset-0 bg-gradient-to-b from-primary/30 to-dark/40"></div>
    </div>
    
    <div class="container mx-auto px-4 z-10 text-center">
      <h1 class="text-[clamp(2.5rem,8vw,5rem)] font-bold text-white text-shadow-lg mb-6 animate-fade-in">
        七夕情人节
      </h1>
      <p class="text-[clamp(1rem,3vw,1.5rem)] text-white text-shadow max-w-3xl mx-auto mb-10 animate-fade-in" style="animation-delay: 0.3s">
        牛郎织女鹊桥会，千年传说永流传
      </p>
      <a href="#story" class="inline-block bg-accent hover:bg-accent/80 text-dark font-bold py-3 px-8 rounded-full shadow-lg transform transition hover:scale-105 animate-fade-in" style="animation-delay: 0.6s">
        探索七夕 <i class="fa fa-arrow-down ml-2"></i>
      </a>
    </div>
    
    <!-- 装饰元素 -->
    <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce">
      <i class="fa fa-angle-double-down text-white text-3xl"></i>
    </div>
    
    <div class="absolute top-20 left-10 w-20 h-20 rounded-full bg-accent/30 animate-float"></div>
    <div class="absolute top-40 right-20 w-16 h-16 rounded-full bg-primary/40 animate-float" style="animation-delay: 1s"></div>
    <div class="absolute bottom-40 left-20 w-12 h-12 rounded-full bg-secondary/50 animate-float" style="animation-delay: 2s"></div>
  </header>

  <!-- 七夕故事部分 -->
  <section id="story" class="py-20 relative">
    <div class="container mx-auto px-4">
      <div class="text-center mb-16">
        <h2 class="text-[clamp(1.8rem,5vw,3rem)] font-bold text-primary mb-4">七夕的传说</h2>
        <div class="w-24 h-1 bg-accent mx-auto"></div>
      </div>
      
      <div class="grid md:grid-cols-2 gap-12 items-center">
        <div class="order-2 md:order-1">
          <h3 class="text-2xl font-bold text-dark mb-6">牛郎织女的爱情故事</h3>
          <p class="mb-4 leading-relaxed">
            传说古代天帝的孙女织女擅长织布，每天给天空织彩霞。她讨厌这枯燥的生活，就偷偷下到凡间，私自嫁给河西的牛郎，过上男耕女织的生活。
          </p>
          <p class="mb-4 leading-relaxed">
            此事惹怒了天帝，把织女捉回天宫，责令他们分离，只允许他们每年的农历七月七日在鹊桥上相会一次。
          </p>
          <p class="mb-6 leading-relaxed">
            每年的这一天，成群的喜鹊会飞来用身体搭成一道跨越天河的喜鹊桥，让牛郎织女得以相会。后来，七夕节也成为了中国的情人节，象征着忠贞不渝的爱情。
          </p>
          <div class="flex items-center space-x-4">
            <i class="fa fa-heart text-primary text-2xl animate-pulse"></i>
            <span class="text-lg italic text-secondary">两情若是久长时，又岂在朝朝暮暮</span>
          </div>
        </div>
        <div class="order-1 md:order-2 relative">
          <div class="rounded-2xl overflow-hidden shadow-2xl transform transition-transform hover:scale-[1.02] duration-500">
            <img src="https://picsum.photos/id/1074/800/600" alt="牛郎织女鹊桥相会" class="w-full h-auto">
          </div>
          <div class="absolute -bottom-6 -left-6 w-24 h-24 bg-accent/20 rounded-full z-[-1]"></div>
          <div class="absolute -top-6 -right-6 w-32 h-32 bg-primary/20 rounded-full z-[-1]"></div>
        </div>
      </div>
    </div>
  </section>

  <!-- 鹊桥动画部分 -->
  <section class="py-16 bg-gradient-romantic relative overflow-hidden">
    <div class="container mx-auto px-4 text-center">
      <h2 class="text-[clamp(1.5rem,4vw,2.5rem)] font-bold text-white text-shadow mb-12">鹊桥相会</h2>
      
      <div class="relative h-64 md:h-80 max-w-4xl mx-auto">
        <!-- 鹊桥 -->
        <div class="absolute bottom-0 left-1/2 transform -translate-x-1/2 w-full max-w-2xl h-40 md:h-56 bg-secondary/30 rounded-t-[100px] overflow-hidden">
          <div class="absolute inset-0 bg-[url('https://picsum.photos/id/1025/1000/500')] bg-cover bg-center opacity-30"></div>
          
          <!-- 喜鹊 -->
          <div class="absolute top-10 left-[20%] w-8 h-8 text-dark transform rotate-45 animate-twinkle" style="animation-delay: 0.2s">
            <i class="fa fa-twitter text-xl"></i>
          </div>
          <div class="absolute top-5 left-[30%] w-8 h-8 text-dark transform -rotate-15 animate-twinkle" style="animation-delay: 0.5s">
            <i class="fa fa-twitter text-xl"></i>
          </div>
          <div class="absolute top-15 left-[40%] w-8 h-8 text-dark transform rotate-30 animate-twinkle" style="animation-delay: 0.8s">
            <i class="fa fa-twitter text-xl"></i>
          </div>
          <div class="absolute top-8 left-[60%] w-8 h-8 text-dark transform -rotate-30 animate-twinkle" style="animation-delay: 1.1s">
            <i class="fa fa-twitter text-xl"></i>
          </div>
          <div class="absolute top-12 left-[70%] w-8 h-8 text-dark transform rotate-15 animate-twinkle" style="animation-delay: 1.4s">
            <i class="fa fa-twitter text-xl"></i>
          </div>
        </div>
        
        <!-- 牛郎 -->
        <div class="absolute bottom-40 left-[30%] w-12 h-20 md:w-16 md:h-24 text-white animate-float" style="animation-delay: 0.5s">
          <i class="fa fa-male text-4xl md:text-5xl"></i>
        </div>
        
        <!-- 织女 -->
        <div class="absolute bottom-40 right-[30%] w-12 h-20 md:w-16 md:h-24 text-white animate-float" style="animation-delay: 1s">
          <i class="fa fa-female text-4xl md:text-5xl"></i>
        </div>
        
        <!-- 星星 -->
        <div class="absolute top-10 left-[10%] w-4 h-4 bg-accent rounded-full animate-twinkle"></div>
        <div class="absolute top-20 left-[85%] w-3 h-3 bg-accent rounded-full animate-twinkle" style="animation-delay: 0.7s"></div>
        <div class="absolute top-5 left-[50%] w-5 h-5 bg-accent rounded-full animate-twinkle" style="animation-delay: 1.2s"></div>
      </div>
    </div>
  </section>

  <!-- 传统习俗部分 -->
  <section id="customs" class="py-20">
    <div class="container mx-auto px-4">
      <div class="text-center mb-16">
        <h2 class="text-[clamp(1.8rem,5vw,3rem)] font-bold text-primary mb-4">七夕传统习俗</h2>
        <div class="w-24 h-1 bg-accent mx-auto mb-6"></div>
        <p class="text-gray-600 max-w-2xl mx-auto">
          七夕节有着悠久的历史和丰富的传统习俗，这些习俗寄托了人们对美好爱情的向往和对幸福生活的追求。
        </p>
      </div>
      
      <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-8">
        <!-- 习俗卡片 1 -->
        <div class="bg-white rounded-xl shadow-lg overflow-hidden transform transition-all duration-300 hover:-translate-y-2 hover:shadow-xl">
          <div class="h-48 overflow-hidden">
            <img src="https://picsum.photos/id/292/600/400" alt="穿针乞巧" class="w-full h-full object-cover transition-transform duration-500 hover:scale-110">
          </div>
          <div class="p-6">
            <h3 class="text-xl font-bold text-dark mb-3">穿针乞巧</h3>
            <p class="text-gray-600">
              女子们在七夕之夜进行穿针比赛，谁能更快地将线穿过针孔，就意味着谁能获得织女的巧艺，嫁个如意郎君。
            </p>
          </div>
        </div>
        
        <!-- 习俗卡片 2 -->
        <div class="bg-white rounded-xl shadow-lg overflow-hidden transform transition-all duration-300 hover:-translate-y-2 hover:shadow-xl">
          <div class="h-48 overflow-hidden">
            <img src="https://picsum.photos/id/431/600/400" alt="拜织女" class="w-full h-full object-cover transition-transform duration-500 hover:scale-110">
          </div>
          <div class="p-6">
            <h3 class="text-xl font-bold text-dark mb-3">拜织女</h3>
            <p class="text-gray-600">
              年轻女子们会在七夕这天准备好瓜果、香烛等物品，向织女祈祷，希望自己能变得心灵手巧，找到理想的伴侣。
            </p>
          </div>
        </div>
        
        <!-- 习俗卡片 3 -->
        <div class="bg-white rounded-xl shadow-lg overflow-hidden transform transition-all duration-300 hover:-translate-y-2 hover:shadow-xl">
          <div class="h-48 overflow-hidden">
            <img src="https://picsum.photos/id/132/600/400" alt="吃巧果" class="w-full h-full object-cover transition-transform duration-500 hover:scale-110">
          </div>
          <div class="p-6">
            <h3 class="text-xl font-bold text-dark mb-3">吃巧果</h3>
            <p class="text-gray-600">
              巧果是七夕节的传统食品，用面粉制成各种花样，然后油炸而成。人们相信吃了巧果能变得心灵手巧。
            </p>
          </div>
        </div>
        
        <!-- 习俗卡片 4 -->
        <div class="bg-white rounded-xl shadow-lg overflow-hidden transform transition-all duration-300 hover:-translate-y-2 hover:shadow-xl">
          <div class="h-48 overflow-hidden">
            <img src="https://picsum.photos/id/118/600/400" alt="种生求子" class="w-full h-full object-cover transition-transform duration-500 hover:scale-110">
          </div>
          <div class="p-6">
            <h3 class="text-xl font-bold text-dark mb-3">种生求子</h3>
            <p class="text-gray-600">
              人们会在七夕前几天，将绿豆、小豆等浸泡发芽，七夕这天用彩线缠绕，祈求多子多福，家族兴旺。
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- 爱情诗句部分 -->
  <section id="poems" class="py-20 bg-primary/10 relative">
    <div class="container mx-auto px-4">
      <div class="text-center mb-16">
        <h2 class="text-[clamp(1.8rem,5vw,3rem)] font-bold text-primary mb-4">经典爱情诗句</h2>
        <div class="w-24 h-1 bg-accent mx-auto"></div>
      </div>
      
      <div class="max-w-4xl mx-auto">
        <div class="relative">
          <!-- 诗句轮播 -->
          <div class="poem-slider overflow-hidden rounded-2xl shadow-xl">
            <div class="poem-slides flex transition-transform duration-500">
              <!-- 诗句 1 -->
              <div class="poem-slide min-w-full bg-white p-8 md:p-12 text-center">
                <p class="text-2xl md:text-3xl italic text-dark mb-6">
                  "两情若是久长时，又岂在朝朝暮暮。"
                </p>
                <p class="text-gray-600">—— 秦观《鹊桥仙·纤云弄巧》</p>
              </div>
              
              <!-- 诗句 2 -->
              <div class="poem-slide min-w-full bg-white p-8 md:p-12 text-center">
                <p class="text-2xl md:text-3xl italic text-dark mb-6">
                  "在天愿作比翼鸟，在地愿为连理枝。"
                </p>
                <p class="text-gray-600">—— 白居易《长恨歌》</p>
              </div>
              
              <!-- 诗句 3 -->
              <div class="poem-slide min-w-full bg-white p-8 md:p-12 text-center">
                <p class="text-2xl md:text-3xl italic text-dark mb-6">
                  "执子之手，与子偕老。"
                </p>
                <p class="text-gray-600">—— 《诗经·邶风·击鼓》</p>
              </div>
              
              <!-- 诗句 4 -->
              <div class="poem-slide min-w-full bg-white p-8 md:p-12 text-center">
                <p class="text-2xl md:text-3xl italic text-dark mb-6">
                  "身无彩凤双飞翼，心有灵犀一点通。"
                </p>
                <p class="text-gray-600">—— 李商隐《无题·昨夜星辰昨夜风》</p>
              </div>
            </div>
          </div>
          
          <!-- 轮播控制按钮 -->
          <button class="absolute top-1/2 left-4 transform -translate-y-1/2 w-10 h-10 bg-primary/80 hover:bg-primary text-white rounded-full flex items-center justify-center shadow-lg transition-all duration-300" id="prevPoem">
            <i class="fa fa-angle-left text-xl"></i>
          </button>
          <button class="absolute top-1/2 right-4 transform -translate-y-1/2 w-10 h-10 bg-primary/80 hover:bg-primary text-white rounded-full flex items-center justify-center shadow-lg transition-all duration-300" id="nextPoem">
            <i class="fa fa-angle-right text-xl"></i>
          </button>
          
          <!-- 轮播指示器 -->
          <div class="flex justify-center space-x-2 mt-6" id="poemIndicators">
            <button class="w-3 h-3 rounded-full bg-primary opacity-100"></button>
            <button class="w-3 h-3 rounded-full bg-primary opacity-50"></button>
            <button class="w-3 h-3 rounded-full bg-primary opacity-50"></button>
            <button class="w-3 h-3 rounded-full bg-primary opacity-50"></button>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- 爱的寄语部分 -->
  <section id="wishes" class="py-20">
    <div class="container mx-auto px-4">
      <div class="text-center mb-16">
        <h2 class="text-[clamp(1.8rem,5vw,3rem)] font-bold text-primary mb-4">爱的寄语</h2>
        <div class="w-24 h-1 bg-accent mx-auto mb-6"></div>
        <p class="text-gray-600 max-w-2xl mx-auto">
          在这个浪漫的日子里，写下你对爱人的祝福，让爱意传递
        </p>
      </div>
      
      <div class="grid md:grid-cols-2 gap-12 items-center">
        <div>
          <form id="wishForm" class="bg-white p-8 rounded-2xl shadow-xl">
            <div class="mb-6">
              <label for="yourName" class="block text-gray-700 mb-2">你的名字</label>
              <input type="text" id="yourName" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent transition-all" placeholder="请输入你的名字">
            </div>
            
            <div class="mb-6">
              <label for="loverName" class="block text-gray-700 mb-2">爱人的名字</label>
              <input type="text" id="loverName" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent transition-all" placeholder="请输入爱人的名字">
            </div>
            
            <div class="mb-6">
              <label for="wishMessage" class="block text-gray-700 mb-2">爱的寄语</label>
              <textarea id="wishMessage" rows="4" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent transition-all" placeholder="写下你想对TA说的话..."></textarea>
            </div>
            
            <button type="submit" class="w-full bg-primary hover:bg-primary/90 text-white font-bold py-3 px-6 rounded-lg shadow transform transition hover:scale-[1.02] duration-300">
              生成爱的寄语 <i class="fa fa-heart ml-2"></i>
            </button>
          </form>
        </div>
        
        <div>
          <div id="wishResult" class="bg-white p-8 rounded-2xl shadow-xl h-full flex flex-col justify-center items-center text-center opacity-0 transition-opacity duration-500">
            <div class="w-20 h-20 bg-primary/20 rounded-full flex items-center justify-center mb-6">
              <i class="fa fa-heart text-primary text-4xl"></i>
            </div>
            <h3 class="text-2xl font-bold text-dark mb-4" id="wishTitle">爱的寄语</h3>
            <div class="w-16 h-1 bg-accent mb-6"></div>
            <p class="text-gray-600 mb-6" id="wishContent">
              你的爱的寄语将会显示在这里...
            </p>
            <p class="text-gray-500 italic" id="wishSignature">
              —— 来自你的爱
            </p>
          </div>
          
          <!-- 默认显示的寄语 -->
          <div id="defaultWish" class="bg-white p-8 rounded-2xl shadow-xl h-full flex flex-col justify-center items-center text-center">
            <div class="w-20 h-20 bg-primary/20 rounded-full flex items-center justify-center mb-6">
              <i class="fa fa-heart text-primary text-4xl animate-pulse"></i>
            </div>
            <h3 class="text-2xl font-bold text-dark mb-4">七夕的祝福</h3>
            <div class="w-16 h-1 bg-accent mb-6"></div>
            <p class="text-gray-600 mb-6">
              愿天下有情人终成眷属，愿每一份爱情都能像牛郎织女般，历经考验而更加坚定。
            </p>
            <p class="text-gray-500 italic">
              —— 七夕的祝福
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- 倒计时部分 -->
  <section class="py-16 bg-dark/90 text-white text-center">
    <div class="container mx-auto px-4">
      <h2 class="text-2xl md:text-3xl font-bold mb-8">距离下一个七夕还有</h2>
      
      <div class="grid grid-cols-2 md:grid-cols-4 gap-4 md:gap-8 max-w-3xl mx-auto">
        <div class="bg-white/10 backdrop-blur-sm rounded-lg p-4 md:p-6">
          <div class="text-3xl md:text-5xl font-bold text-accent mb-2" id="days">00</div>
          <div class="text-sm md:text-base">天</div>
        </div>
        <div class="bg-white/10 backdrop-blur-sm rounded-lg p-4 md:p-6">
          <div class="text-3xl md:text-5xl font-bold text-accent mb-2" id="hours">00</div>
          <div class="text-sm md:text-base">时</div>
        </div>
        <div class="bg-white/10 backdrop-blur-sm rounded-lg p-4 md:p-6">
          <div class="text-3xl md:text-5xl font-bold text-accent mb-2" id="minutes">00</div>
          <div class="text-sm md:text-base">分</div>
        </div>
        <div class="bg-white/10 backdrop-blur-sm rounded-lg p-4 md:p-6">
          <div class="text-3xl md:text-5xl font-bold text-accent mb-2" id="seconds">00</div>
          <div class="text-sm md:text-base">秒</div>
        </div>
      </div>
    </div>
  </section>

  <!-- 页脚 -->
  <footer class="bg-primary text-white py-10">
    <div class="container mx-auto px-4">
      <div class="flex flex-col md:flex-row justify-between items-center">
        <div class="mb-6 md:mb-0">
          <div class="flex items-center space-x-2 mb-2">
            <i class="fa fa-heart text-accent text-xl animate-pulse"></i>
            <span class="text-xl font-bold">七夕浪漫夜</span>
          </div>
          <p class="text-white/80 text-sm">愿天下有情人终成眷属</p>
        </div>
        
        <div class="flex space-x-6 mb-6 md:mb-0">
          <a href="#" class="text-white hover:text-accent transition-colors duration-300">
            <i class="fa fa-weibo text-xl"></i>
          </a>
          <a href="#" class="text-white hover:text-accent transition-colors duration-300">
            <i class="fa fa-wechat text-xl"></i>
          </a>
          <a href="#" class="text-white hover:text-accent transition-colors duration-300">
            <i class="fa fa-instagram text-xl"></i>
          </a>
          <a href="#" class="text-white hover:text-accent transition-colors duration-300">
            <i class="fa fa-facebook text-xl"></i>
          </a>
        </div>
        
        <div class="text-white/80 text-sm">
          &copy; 2023 七夕情人节 | 浪漫永恒
        </div>
      </div>
    </div>
  </footer>

  <!-- 返回顶部按钮 -->
  <button id="backToTop" class="fixed bottom-8 right-8 w-12 h-12 bg-primary text-white rounded-full flex items-center justify-center shadow-lg transform transition-all duration-300 opacity-0 invisible hover:bg-primary/90">
    <i class="fa fa-arrow-up"></i>
  </button>

  <!-- JavaScript -->
  <script>
    // 生成星星背景
    function createStars() {
      const starsContainer = document.getElementById('stars');
      const starCount = 100;
      
      for (let i = 0; i < starCount; i++) {
        const star = document.createElement('div');
        const size = Math.random() * 3 + 1;
        const opacity = Math.random() * 0.8 + 0.2;
        
        star.style.position = 'absolute';
        star.style.width = `${size}px`;
        star.style.height = `${size}px`;
        star.style.backgroundColor = 'white';
        star.style.borderRadius = '50%';
        star.style.left = `${Math.random() * 100}%`;
        star.style.top = `${Math.random() * 100}%`;
        star.style.opacity = opacity;
        star.style.animation = `twinkle ${Math.random() * 3 + 2}s ease-in-out infinite`;
        star.style.animationDelay = `${Math.random() * 3}s`;
        
        starsContainer.appendChild(star);
      }
    }
    
    // 移动端菜单切换
    function setupMobileMenu() {
      const menuToggle = document.getElementById('menuToggle');
      const mobileMenu = document.getElementById('mobileMenu');
      
      menuToggle.addEventListener('click', () => {
        mobileMenu.classList.toggle('hidden');
      });
    }
    
    // 诗句轮播
    function setupPoemSlider() {
      const slidesContainer = document.querySelector('.poem-slides');
      const slides = document.querySelectorAll('.poem-slide');
      const prevBtn = document.getElementById('prevPoem');
      const nextBtn = document.getElementById('nextPoem');
      const indicators = document.querySelectorAll('#poemIndicators button');
      
      let currentIndex = 0;
      const slideCount = slides.length;
      
      function updateSlider() {
        slidesContainer.style.transform = `translateX(-${currentIndex * 100}%)`;
        
        // 更新指示器
        indicators.forEach((indicator, index) => {
          if (index === currentIndex) {
            indicator.style.opacity = '1';
          } else {
            indicator.style.opacity = '0.5';
          }
        });
      }
      
      prevBtn.addEventListener('click', () => {
        currentIndex = (currentIndex - 1 + slideCount) % slideCount;
        updateSlider();
      });
      
      nextBtn.addEventListener('click', () => {
        currentIndex = (currentIndex + 1) % slideCount;
        updateSlider();
      });
      
      // 点击指示器切换
      indicators.forEach((indicator, index) => {
        indicator.addEventListener('click', () => {
          currentIndex = index;
          updateSlider();
        });
      });
      
      // 自动轮播
      setInterval(() => {
        currentIndex = (currentIndex + 1) % slideCount;
        updateSlider();
      }, 5000);
    }
    
    // 爱的寄语表单提交
    function setupWishForm() {
      const form = document.getElementById('wishForm');
      const result = document.getElementById('wishResult');
      const defaultWish = document.getElementById('defaultWish');
      const wishTitle = document.getElementById('wishTitle');
      const wishContent = document.getElementById('wishContent');
      const wishSignature = document.getElementById('wishSignature');
      
      form.addEventListener('submit', (e) => {
        e.preventDefault();
        
        const yourName = document.getElementById('yourName').value || '我';
        const loverName = document.getElementById('loverName').value || '你';
        const message = document.getElementById('wishMessage').value || '愿我们的爱情像牛郎织女一样，跨越一切阻碍，永远相守。';
        
        wishTitle.textContent = `${yourName} 对 ${loverName} 的七夕祝福`;
        wishContent.textContent = message;
        wishSignature.textContent = `—— 爱你的 ${yourName}`;
        
        // 显示结果，隐藏默认寄语
        defaultWish.style.display = 'none';
        result.style.opacity = '0';
        result.style.display = 'flex';
        
        // 淡入效果
        setTimeout(() => {
          result.style.opacity = '1';
        }, 100);
        
        // 滚动到结果区域
        result.scrollIntoView({ behavior: 'smooth', block: 'center' });
      });
    }
    
    // 倒计时功能
    function setupCountdown() {
      // 计算下一个七夕（农历七月初七）的日期
      function getNextQixi() {
        const now = new Date();
        let year = now.getFullYear();
        
        // 农历转公历的大致日期（实际应用中需要更精确的转换库）
        // 这里简化处理，假设每年七夕在公历8月14日左右
        let qixi = new Date(year, 8, 29); // 8月14日
        
        // 如果今年的七夕已过，则计算明年的
        if (qixi < now) {
          qixi = new Date(year + 1, 7, 14);
        }
        
        return qixi;
      }
      
      function updateCountdown() {
        const qixi = getNextQixi();
        const now = new Date();
        const diff = qixi - now;
        
        const days = Math.floor(diff / (1000 * 60 * 60 * 24));
        const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
        const seconds = Math.floor((diff % (1000 * 60)) / 1000);
        
        document.getElementById('days').textContent = days.toString().padStart(2, '0');
        document.getElementById('hours').textContent = hours.toString().padStart(2, '0');
        document.getElementById('minutes').textContent = minutes.toString().padStart(2, '0');
        document.getElementById('seconds').textContent = seconds.toString().padStart(2, '0');
      }
      
      // 初始化并每秒更新一次
      updateCountdown();
      setInterval(updateCountdown, 1000);
    }
    
    // 返回顶部按钮
    function setupBackToTop() {
      const backToTopBtn = document.getElementById('backToTop');
      
      window.addEventListener('scroll', () => {
        if (window.pageYOffset > 300) {
          backToTopBtn.classList.remove('opacity-0', 'invisible');
          backToTopBtn.classList.add('opacity-100', 'visible');
        } else {
          backToTopBtn.classList.remove('opacity-100', 'visible');
          backToTopBtn.classList.add('opacity-0', 'invisible');
        }
        
        // 导航栏滚动效果
        const navbar = document.getElementById('navbar');
        if (window.pageYOffset > 100) {
          navbar.classList.add('py-2', 'bg-primary');
          navbar.classList.remove('py-3', 'bg-primary/90');
        } else {
          navbar.classList.add('py-3', 'bg-primary/90');
          navbar.classList.remove('py-2', 'bg-primary');
        }
      });
      
      backToTopBtn.addEventListener('click', () => {
        window.scrollTo({ top: 0, behavior: 'smooth' });
      });
    }
    
    // 平滑滚动
    function setupSmoothScroll() {
      document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function (e) {
          e.preventDefault();
          
          const targetId = this.getAttribute('href');
          const targetElement = document.querySelector(targetId);
          
          if (targetElement) {
            targetElement.scrollIntoView({
              behavior: 'smooth'
            });
            
            // 关闭移动菜单（如果打开）
            document.getElementById('mobileMenu').classList.add('hidden');
          }
        });
      });
    }
    
    // 页面加载完成后初始化
    document.addEventListener('DOMContentLoaded', () => {
      createStars();
      setupMobileMenu();
      setupPoemSlider();
      setupWishForm();
      setupCountdown();
      setupBackToTop();
      setupSmoothScroll();
    });
  </script>
</body>
</html>
