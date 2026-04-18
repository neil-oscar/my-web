# Web Design Specification

## 1. Visual Theme & Atmosphere
- **Philosophy**: 活力极客与友好科技（Vibrant Tech & Friendly AI）
- **Keywords**: 动态（Dynamic）、年轻（Youthful）、专业（Professional）、亲和力（Affinity）、光怪陆离（Luminous）
- **Tagline**: 用专业的技术能力，赋予冰冷机械以温暖的智能。
- **Reference Match**: 从原本硬核工业黑红风格，转向深色玻璃拟物化（Glassmorphism）+ 极光渐变（Aurora Gradients），辅以可爱的机器人元素。既保留了前沿科技的专业感，又大幅提升了年轻人的活力与亲和力。

## 2. Color Palette & Roles
`css
:root {
  /* Base Backgrounds */
  --bg-base: #030712;        /* Darker obsidian */
  --bg-surface: rgba(255, 255, 255, 0.03); /* Glassmorphism */
  --bg-surface-hover: rgba(255, 255, 255, 0.08);

  /* Accents (Vibrant & Young) */
  --accent-primary: #0ea5e9; /* Sky Blue 活力蓝 */
  --accent-secondary: #8b5cf6; /* Violet 梦幻紫 */
  --accent-warm: #ec4899; /* Pink 温暖粉 */
  --accent-hover: #38bdf8;
  --accent-glow: rgba(14, 165, 233, 0.5);

  /* Typography */
  --text-primary: #f8fafc;
  --text-secondary: #cbd5e1;
  --text-muted: #64748b;

  /* UI Elements */
  --border-color: rgba(255, 255, 255, 0.1);
}
`

## 3. Typography Rules
- **Font Families**:
  - English: Inter, DM Sans, sans-serif
  - Chinese: Noto Sans SC, PingFang SC, sans-serif
- **Hierarchy**:
  - H1 (Hero): 4rem (Desktop) / 2.5rem (Mobile), Font Weight 800, 增加渐变色文字效果（Gradient Text）
  - H2 (Section): 2.5rem (Desktop) / 1.75rem (Mobile), Font Weight 700 
  - H3 (Card Title): 1.25rem, Font Weight 600
  - Body: 1rem (16px), Line Height 1.75, Letter Spacing 0.02em

## 4. Component Stylings
- **Primary Button**: 渐变背景 (linear-gradient(to right, var(--accent-primary), var(--accent-secondary)))，hover 时带有强烈的发光阴影与轻微的 scale 放大，大圆角 (ounded-full) 以增加亲和力。
- **Secondary/Tech Pill**: 半透明玻璃态背景 (ar(--bg-surface)), 彩色发光边框 (order-color: var(--accent-primary)), hover 时背景色加深。
- **Project Cards**: 玻璃拟物化卡片，ackdrop-filter: blur(12px)，边框渐变高光，Hover 时浮动 (	ranslateY(-8px))，带有生动的聚光灯（Spotlight）效果。

## 5. Layout Principles
- **Grid System**: 12-column CSS Grid / Flexbox 结构，打破死板的绝对对齐，增加动态呼吸感。
- **Max Width**: max-w-7xl (1280px) 加上左右充足的安全边距。
- **Spacing**: 更大的留白 (py-32) 代替紧凑布局，让背景的极光色块透出来。

## 6. Depth & Elevation
- **Aurora Gradients**: 页面底层放置若干个巨大尺寸、高斯模糊的彩色色块（蓝、紫、粉），通过 CSS animate 缓慢漂浮交融，形成极光/晶体渲染质感。
- **Glassmorphism**: 卡片使用半透明白色填充+背景模糊，取代死板的黑色。
- **Drop Shadows**: 卡片 hover 时增加大范围的彩色弥散阴影 (ox-shadow: 0 20px 40px -10px rgba(139, 92, 246, 0.2))。

## 7. Animation & Interaction (L3 - 沉浸体验 / 动态活力)
- **Entrance (Hero)**: 文字带有生动的梯度入场；引入右侧悬浮的“可爱机器人”（通过 CSS 动画实现呼吸、浮动效果）。
- **Scroll Reveal**: GSAP 层叠滚动动画（Staggered reveal），卡片进入视窗时不仅透明度变化，还有少许旋转和缩放（Spring 弹簧效果）。
- **Spotlight Hover**: 鼠标悬停在卡片上时，卡片边缘或内部出现跟随鼠标的光晕。
- **Background Motion**: 底层极光色块持续 20s 一个周期的柔和流转动画。

## 8. Do's and Don'ts
- **Do**: 使用高明度、高饱和度的渐变色（蓝紫粉），彰显年轻态和未来感。
- **Do**: 采用大圆角（ounded-2xl, ounded-full），削弱工业风的生冷感，增加亲和力。
- **Do**: 保持背景极其深邃（#030712），使得渐变极光和文字层更加通透跃出。
- **Do**: 加入微动态互动反馈，如按钮点击涟漪、悬停发光。
- **Don't**: 不再使用大面积的纯黑色 #000 或 #111 实体框。
- **Don't**: 避开警示红、血红色，以免产生压力或过度硬核感。
- **Don't**: 动画不要过于跳脱或混乱导致眩晕，保持专业工程师的稳重克制。

## 9. Responsive Behavior
- **Mobile (< 768px)**: 极光背景斑点缩小并降低模糊率，保证性能；Hero 区文字缩小，机器人缩略或置于文字下方。
- **Tablet (768px - 1024px)**: 2-column grids for cards。
- **Desktop (> 1024px)**: Full fluid layouts, immersive hover interactions.
