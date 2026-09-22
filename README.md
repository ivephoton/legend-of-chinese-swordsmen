# 蜀山剑侠·天劫录 · Legend of Chinese Swordsmen

> 以还珠楼主《蜀山剑侠传》为背景、仿《天地劫》玩法的网页战棋游戏。
> 单个 HTML 文件，打开即玩，无需安装、无需构建。

**[English summary below](#english)**

---

## 目录
- [在线游玩](#在线游玩)
- [游戏特色](#游戏特色)
- [操作说明](#操作说明)
- [核心系统](#核心系统)
- [角色一览](#角色一览)
- [章回结构](#章回结构)
- [存档与进度](#存档与进度)
- [技术说明](#技术说明)
- [部署到 GitHub Pages](#部署到-github-pages)
- [本地运行](#本地运行)
- [已知限制](#已知限制)
- [致谢与版权](#致谢与版权)

---

## 在线游玩

开启 GitHub Pages 后访问：

```
https://<你的用户名>.github.io/legend-of-chinese-swordsmen/
```

也可以直接用浏览器打开仓库里的 `index.html`。推荐使用新版 Chrome、Edge、Safari 或 Firefox，手机和电脑均可。

---

## 游戏特色

| 类别 | 内容 |
|---|---|
| 章回 | 30 回主线，终章为「三次峨眉斗剑」三连战，每回有开场与终章剧情 |
| 角色 | 20 位可控侠士随剧情登场，各有独立外貌、本命飞剑与专属剑招 |
| 道法 | 100 种道法（金木水火土各 20），按名称意象配有不同的施法动画 |
| 法宝 | 100 件法宝（飞剑、法器、护身），击败敌人或开启宝箱获得 |
| 地图 | 45 度立体沙盘，26×20 格，高低地势、蜿蜒河流、木桥、厚土底座 |
| 演出 | 机战式战斗画面：切入台词、招式名、飞剑残影、受创 / 闪避 / 防御三种表现 |
| 音乐 | 洞府与战斗各有配乐（笛、古筝、太鼓），全部实时合成 |
| 界面 | 古风回纹边框、木牌按钮、楷书字体 |

---

## 操作说明

### 战场
| 操作 | 电脑 | 手机 |
|---|---|---|
| 选择角色 / 移动 / 选目标 | 左键点击 | 轻点 |
| 缩放地图 | 鼠标滚轮 | 双指捏合 |
| 平移地图 | 拖动 | 单指拖动 |
| 复位视角 | 双击地图 | 双击地图 |
| 返回上一步 | 右键 或 Esc | 点菜单中的「返回 / 取消」 |
| 停止全自动 | P 键 或「停止全自动」按钮 | 「停止全自动」按钮 |

### 一次行动的流程
1. 点击己方角色，亮起的格子为可移动范围。
2. 点击目标格移动（点角色本身则原地行动）。
3. 角色身旁弹出指令菜单：**攻击 / 法术 / 待机 / 取消**。
4. 选定目标后，右上角出现战斗预测（伤害、命中率、能否反击、五行克制），点击「出手」或「施展」确认。

### 其他
- **点击空白处**：打开系统菜单（结束回合、委托本回合、全自动、战斗画面开关、音乐、保存进度、重新开始本战、撤退）。
- **点击敌人**：显示其移动范围（粉紫）与攻击范围（红）。
- **点击属性名**（气血、身法、命中等）：弹出属性说明。

---

## 核心系统

### 五行相克
金克木、木克土、土克水、水克火、火克金。克制方伤害 +30%，被克方 −20%。

### 命中与闪避
- 闪避几率 = 防守方 **身法** − 攻击方 **命中**（范围 0%～80%）。
- 普通攻击与伤害类道法都可以被闪避；被定身者无法闪避。

### 敌袭应对
敌人攻击我方时可选择（9 秒倒计时，默认反击）：
| 选项 | 效果 |
|---|---|
| 反击 | 照常受创，随后还以普通攻击 |
| 防御 | 伤害降至 55% |
| 回避 | 闪避率 +25%；失败则受创 115% |

### 地形效果
诸侠御剑飞行，移动**不受地形阻隔**，但地形仍影响战斗：

| 地形 | 效果 |
|---|---|
| 平地 | 金、火行伤害 +8% |
| 林 | 闪避 +10，木行伤害 +15% |
| 山 | 命中 +8，受创 −20%，土行伤害 +15% |
| 水 | 闪避 −10，受创 +10%（水行免疫），水行伤害 +20% |
| 高地 | 居高临下命中 +6，仰攻高处命中 −6 |

### 境界与成长
- 每 100 修为升一级；每 10 级为一重境界：**练气 → 筑基 → 金丹 → 元婴 → 化神 → 渡劫 → 大乘**，每重境界全属性再 +4%。
- **金钱**：击败敌人（首领 5 倍）、通关、开启宝箱获得。
- **修炼**：在洞府的侠士详情页花金钱提升气血、剑力、护体、法力、抗法、身法、命中、真元，每项最多 30 级。

### 胜负条件
每回各有条件，出阵前与战斗顶栏均会显示，例如：歼灭全部敌人、击败首领、护送指定角色、限定回合内取胜、坚守若干回合。

### 失败不清零
战斗失败时，本战获得的**等级、修为、金钱与法宝全部保留**，可一键「重新开始本战」。

### 宝箱
每张地图有 2～3 个宝箱，角色移动到该格即自动开启，屏幕中央提示获得的金钱或法宝。

---

## 角色一览

| 侠士 | 五行 | 职业 | 本命飞剑 | 登场 |
|---|---|---|---|---|
| 李英琼 | 金 | 剑仙 | 紫郢剑 | 第一回 |
| 李宁 | 金 | 佛门 | 降魔金刚剑 | 第一回 |
| 周轻云 | 水 | 剑仙 | 青索剑 | 第二回 |
| 齐灵云 | 土 | 法修 | 霞光仙剑 | 第三回 |
| 齐金蝉 | 金 | 剑仙 | 霹雳金剑 | 第三回 |
| 笑和尚 | 火 | 佛门 | 无形剑 | 第四回 |
| 朱文 | 金 | 法修 | 天遁霞剑 | 第五回 |
| 严人英 | 水 | 剑仙 | 碧海寒锋 | 第六回 |
| 石生 | 土 | 剑仙 | 玉灵剑 | 第七回 |
| 余英男 | 火 | 剑仙 | 南明离火剑 | 第八回 |
| 醉道人 | 木 | 散仙 | 醉仙剑 | 第九回 |
| 秦紫玲 | 火 | 法修 | 紫霞剑 | 第十回 |
| 秦寒萼 | 水 | 法修 | 冰萼剑 | 第十回 |
| 司徒平 | 木 | 剑仙 | 乌龙剑 | 第十一回 |
| 申若兰 | 木 | 法修 | 桃花剑 | 第十二回 |
| 追云叟 | 土 | 散仙 | 追云剑 | 第十三回 |
| 癞姑 | 木 | 佛门 | 屠龙剑 | 第十五回 |
| 易静 | 火 | 散仙 | 神婴剑 | 第十七回 |
| 郑八姑 | 水 | 散仙 | 雪魄剑 | 第十九回 |
| 凌浑 | 土 | 散仙 | 游龙剑 | 第二十一回 |

---

## 章回结构

- **第一回～第二十九回**：莽苍山紫郢出世、慈云寺、青螺峪、百蛮山诛绿袍、峨眉开府、幻波池、紫云宫、大雪山、赤身教、华山烈火祖师、血河大阵、心魔劫……
- **第三十回 · 三次峨眉斗剑**
  1. 第一次斗剑 · 慈云余孽
  2. 第二次斗剑 · 群邪会战
  3. 第三次斗剑 · 万劫归一

已通关的章回可随时重打，用来积累修为、金钱和收集法宝。

---

## 存档与进度

- 进度**自动保存**在浏览器的 localStorage 中。
- **存档码**：洞府的「存档码」按钮或战斗中系统菜单的「保存进度」，会显示一段以 `SS1-` 开头的存档码。
- **恢复进度**：在标题画面点「输入存档码」，粘贴后即可恢复，可用于换浏览器、换设备或备份。

> 清空浏览器数据会删除本地进度，重要进度请保存存档码。

---

## 技术说明

- **单文件**：全部 HTML、CSS、JavaScript 都在 `index.html` 中。
- **3D 模型**：人物、飞剑、树木、山石、宝箱均由 [three.js](https://threejs.org/)（r128）在运行时用几何体程序化生成，再渲染为立绘与头像；不依赖任何外部模型文件。
- **地图**：CSS 3D 变换构建 45 度立体沙盘，地面纹理由 Canvas 实时绘制。
- **音频**：WebAudio 实时合成配乐与音效，无音频文件。
- **外部依赖**（均通过 CDN 加载）：
  - three.js r128 — `cdnjs.cloudflare.com`
  - Google Fonts（Noto Serif SC、ZCOOL XiaoWei、Ma Shan Zheng、Zhi Mang Xing）
- **字体**：若系统已安装方正盛世楷书、方正榜书行、禹卫书法行书，会优先使用；否则回退到系统楷体或网络字体。

---

## 部署到 GitHub Pages

1. 将 `index.html`、`README.md` 推送到仓库的 `main` 分支根目录。
2. 进入仓库 **Settings → Pages**。
3. **Source** 选择 *Deploy from a branch*，Branch 选 `main`，目录选 `/ (root)`，点击 **Save**。
4. 等待一两分钟，访问 `https://<你的用户名>.github.io/<仓库名>/`。

---

## 本地运行

直接双击 `index.html` 即可。如需本地服务器：

```bash
# Python 3
python -m http.server 8000
# 然后访问 http://localhost:8000
```

---

## 已知限制

- 首次进入某种风格的地图时需要现场生成地形与人物模型，会有短暂的「布阵中」等待，之后同类地图会复用。
- 人物为程序化生成的低多边形风格，无法达到专业建模加贴图的写实程度。
- 浏览器要求用户先点击一次页面后才能播放声音。
- 需要浏览器支持 WebGL；不支持时会自动退回二维棋子与印章头像。

---

## 致谢与版权

- 故事与人物取材自还珠楼主（李寿民）《蜀山剑侠传》，原著已进入公有领域。
- 玩法参考《天地劫》系列与《超级机器人大战》系列的战棋与演出形式。
- 本项目代码与美术均为原创实现。

---

<a id="english"></a>
## English Summary

**Legend of Chinese Swordsmen** (蜀山剑侠·天劫录) is a browser-based tactical RPG inspired by the *Tiandijie* series, set in the world of Huanzhu Louzhu's classic wuxia novel *Legend of the Swordsmen of the Mountains of Shu*.

- **Single HTML file**: open `index.html` and play, with no install and no build step.
- **Content**: 30 chapters (the finale is the three Emei Sword Duels), 20 playable heroes each with a unique flying sword and signature attack, 100 spells, 100 treasures.
- **Map**: 45° isometric diorama (26×20 tiles) with elevation, rivers, bridges and treasure chests.
- **Combat**: Super Robot Wars–style command menus and battle cut-ins, five-element counters, agility-vs-accuracy dodge, and a counter / guard / evade choice when enemies attack.
- **Progression**: cultivation realms, gold-based stat training, per-chapter win/lose conditions. Levels, gold and items are kept on defeat.
- **Controls**: click or tap to act, mouse wheel or pinch to zoom, drag to pan, double-click to reset the view. Press P to stop auto-battle.
- **Saves**: automatic local save, plus exportable save codes (`SS1-…`) you can paste on the title screen to restore progress on any device.
- **Tech**: vanilla JS, three.js r128 for procedurally generated models, CSS 3D for the board, Canvas for terrain painting, WebAudio for synthesized music.
