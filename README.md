# LudotsSample

Ludots 大体积样本资产仓库（大文件走 Git LFS：`git lfs install && git lfs pull`）。主仓 [MightyBubble/Ludots](https://github.com/MightyBubble/Ludots)
不放超过 GitHub 单文件限制或显著膨胀克隆体积的生成资产；此类资产在此托管，
按来源分支与生成工具留档，可随时再生或回填。

## east_asia/

东亚可玩地形 showcase 的大体积生成资产（源分支 `codex/east-asia-playable-terrain`，本地工作树
`LudotsProd-east-asia-playable-terrain`，2026-08 快照）：

| 文件 | 大小 | 说明 |
|---|---|---|
| `east_asia_hex.vtxm` | 141 MB | Hex VertexMap 地形数据。超过 GitHub 100MB 单文件限制，本仓以 **Git LFS** 托管（克隆后 `git lfs pull` 拉取实体） |
| `east_asia_continuous.vhtm` | 57 MB | 连续 VisualHeightmap 地形 |

### 回填位置

```
Ludots/mods/showcases/east_asia_playable_terrain/EastAsiaPlayableTerrainMod/assets/
├── Data/Maps/east_asia_hex.vtxm
└── terrain/east_asia_continuous.vhtm
```

### 再生方式

源分支内的工具链生成（不在本仓）：

- `src/Tools/Ludots.Tool/EastAsiaTerrainAssetGenerator.cs`（地形资产生成器）
- `src/Tools/Ludots.Tool/TerrainControlMapBaker.cs`（控制图烘焙）
- CLI：`ludots` 工具的 east-asia 生成命令（见该分支 `Program.cs`）

源分支后续应改为"首次运行下载/生成本资产"而非直接提交进主仓。

## 校验和（SHA-256）

```
4fb59c9eec450d301b405bd336cf37cc2b221532e8dbad6186de10ac89ff8293  east_asia/east_asia_hex.vtxm
537704c2832d5b25c4ebeb4b9f781959e56badd0d2d5ecd68ff0922d28e94487  east_asia/east_asia_continuous.vhtm
```
