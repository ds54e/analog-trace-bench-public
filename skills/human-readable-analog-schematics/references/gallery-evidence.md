# Gallery evidence / 作例から得た判断

観察日：2026-10-11。ユーザーのログイン後、[指定ギャラリー](https://analog-canvas.tokenzhang.com/?ai=0)の `ai=0` 絞り込みを確認。表示件数889件、取得した先頭ページ60件から、OTA・補償・LDO・バイアスを含む13件を選び、SVGプレビューをブラウザーで表示して目視比較した。全件を評価したものではない。

`ai=0` は保存された `ai_generated=0` に対応する（[実装](https://github.com/cascode-ai/analog-canvas/blob/37bccd4012764dce53b34927fa606c6f430296a2/worker/gallery-store-wall.ts#L206)）。個々の制作過程・著者性を別途確認したわけではない。作例の回路動作・接続・値の正しさを検証する調査ではなく、図の読みやすさを観察した。閲覧リンクはログインを要する場合がある。

「観察」は図から読み取れる特徴、「次回への示唆」はそこから導いた作図上の判断。読みやすさの保証や公式規格ではない。表示著者名はギャラリーの記載であり、論文・教科書の原著者とは限らない。

## 差動枝の対称性

[Continuous-Time Comparator with Preamplifier](https://analog-canvas.tokenzhang.com/api/gallery/8nm6fak8ez/preview.svg) — 表示著者：Magic Li、ID `8nm6fak8ez`。

**観察／採用したい特徴：** 左右のMOSが行ごとに揃い、対応する枝と共通点が形で読める。主回路と後段・スイッチが空間的に分かれる。

**注意／適用の限界：** 密な中央のVCM・抵抗周辺は文字の余裕が少ない。対称性を採用し、文字密度まで真似ない。

## ミラーの共通ゲート

[Self Bias Circuit](https://analog-canvas.tokenzhang.com/api/gallery/zp3r9haqg7/preview.svg) — 表示著者：Zengchun Chen、ID `zp3r9haqg7`。

**観察／採用したい特徴：** 上部のM1/M2/M5の共通ゲートと短いD–G帰還、右側の二つのバイアス出力が見える。

**注意／適用の限界：** 左右対称そのものが目的ではない。自己バイアスの戻り経路があるため、単純な左→右の図に変形しない。

## 補償の接続先

[Miller Compensation of Two Stage AMP with Voltage Buffer](https://analog-canvas.tokenzhang.com/api/gallery/fy4qb94fzy/preview.svg) — 表示著者：Zengchun Chen、ID `fy4qb94fzy`。

**観察／採用したい特徴：** 入力と出力を左右に置き、主増幅の線とCcの枝を上下に分ける。Ccがバッファ側へつながることを線で追える。

**注意／適用の限界：** これは電圧バッファ付き補償の作例。ATBの直列RCへトポロジーを転用しない。

## 主経路と補助枝

[Miller Compensation With Current Buffer](https://analog-canvas.tokenzhang.com/api/gallery/a2nn9n6pbn/preview.svg) — 表示著者：Zengchun Chen、ID `a2nn9n6pbn`。

**観察／採用したい特徴：** 下側の入力から次段ゲートへ向かう線と、上側のCcの枝を分離。局所電源・接地記号で大きな外枠を作らない。

**注意／適用の限界：** 図が簡潔でも値やモデルを省略した概念図である。実ネットリストからの図には全値を保持する別表や詳細表示が必要。

## 機能だけを補助色で強調

[OTA including passives for frequency compensation.](https://analog-canvas.tokenzhang.com/api/gallery/xd4knhb9f5/preview.svg) — 表示著者：Magic Li、ID `xd4knhb9f5`。

**観察／採用したい特徴：** 主回路の黒に対し、補償の受動素子を緑、gmブロックを青で示す。入力側から出力側へ段が並ぶ。

**注意／適用の限界：** 色枠と配線が密になる箇所もある。色は説明用で、接続や極性を色だけに任せない。

## 大回路の分割

[Two Stage OTA with Flying Cap CMFB](https://analog-canvas.tokenzhang.com/api/gallery/cwmesegne8/preview.svg) — 表示著者：Zengchun Chen、ID `cwmesegne8`。

**観察／採用したい特徴：** 主OTAを左、スイッチトキャパシタCMFBを右上、バイアスを右下に配置。主OTAの左右の対称な対応が残る。

**注意／適用の限界：** ブロック間はラベル参照になる。主ループの説明を目的とする場合は全体の接続図も添える。短い斜めクロス線は対応を示す例外。

## 機能と補助回路の階層

[Telescopic OTA with CMFB and Bias](https://analog-canvas.tokenzhang.com/api/gallery/cbmzkzbr8x/preview.svg) — 表示著者：Zengchun Chen、ID `cbmzkzbr8x`。

**観察／採用したい特徴：** 左に積み重ねた対称なOTA、中ほどにCMFB、右に独立したバイアス回路。局所ごとの電源範囲を保つ。

**注意／適用の限界：** 横長なので小さい画面では文字が小さくなる。詳細ビューの分割も必要。色枠の重なりまで作図ルールにしない。

## 複雑さに対する段組み

[amplifier including a folded cascode differential gain stage, the biasing circuit and second gain stage.](https://analog-canvas.tokenzhang.com/api/gallery/dsf2ff78pp/preview.svg) — 表示著者：Magic Li、ID `dsf2ff78pp`。

**観察／採用したい特徴：** 左のバイアス、中央の入力・増幅部、右の出力段へ配置が進む。同じ素子段を水平に揃える。

**注意／適用の限界：** 多数の横断配線が残り、ひと目で理解できる万能な作例ではない。ATBの少数素子回路ではもっと短くまとめられる。

## LDOの機能順

[LDO regulator’s core structure](https://analog-canvas.tokenzhang.com/api/gallery/pes3mh8swm/preview.svg) — 表示著者：Magic Li、ID `pes3mh8swm`。

**観察／採用したい特徴：** 誤差増幅器→バッファ→出力段を左から右へ並べ、分圧器を出力の下に置く。

**注意／適用の限界：** Vfbはラベルで分断される。この作例の段配置を採用しつつ、閉ループ説明用のATB図では帰還線を見せる。

## LDOの帰還通路

[LDO regulator](https://analog-canvas.tokenzhang.com/api/gallery/8qatzztvzk/preview.svg) — 表示著者：Magic Li、ID `8qatzztvzk`。

**観察／採用したい特徴：** 右側の分圧器中点から入力側へ下端の戻り線を確保している。入力・増幅・パス段の並びと合わせ、帰還先を追える。

**注意／適用の限界：** 試験用と思われる開口・ラベルが入力近傍にある。電気的連続性をこのプレビューだけで保証しない。中央の交差が多い点も残る。

## 局所対称と外周配線

[low-dropout regulator](https://analog-canvas.tokenzhang.com/api/gallery/g6b58gnemm/preview.svg) — 表示著者：Magic Li、ID `g6b58gnemm`。

**観察／採用したい特徴：** 左の対称な増幅部、上部の補償枝、右側の出力側回路が空間的に分かれる。長い線を外周へ逃がしている。

**注意／適用の限界：** C4表記が複数あり、VOUTも別位置のラベル参照になっている。見た目を元に接続・識別子の正しさまで信用しない。

## 過密化の比較例

[LDO](https://analog-canvas.tokenzhang.com/api/gallery/66fgy9aetr/preview.svg) — 表示著者：Magic Li、ID `66fgy9aetr`。

**観察／採用したい特徴：** 縦の枝と素子行が揃うので、各局所構造は認識できる。

**注意／適用の限界：** 全体の素子数と横幅が大きく、複数のVoutラベルもある。全体図＋詳細図を分ける判断の参考にする。小回路でこの密度・横幅を再現しない。

## バイアスの役割分け

[Bias structure](https://analog-canvas.tokenzhang.com/api/gallery/ck79hnz2xw/preview.svg) — 表示著者：Magic Li、ID `ck79hnz2xw`。

**観察／採用したい特徴：** 左・中央・右の部分に役割を示し、共通ゲートの横線と枝の縦線を整える。

**注意／適用の限界：** 色枠の外にも関連素子があり、見出しだけでは全接続を説明しきれない。機能境界の正しさは元ネットリストで確認する。

## 前回のATB図との違い

作例は、MOSの機能的なまとまり、局所的な対称性、短い共通ゲート配線、近接した段間関係を使っている。前回のATB図は接続比較を通した一方、少数の素子を広く配置し、主要な関係の一部を離れた同名ラベルへ任せていた。文字が重ならないだけでは、この差は検出できなかった。

数値サイズの見せ方は別問題。ギャラリーにはW/Lや値を省略した図も多いので、その簡潔さを得るために元のSPICE値を捨ててはならない。読み取り用の図と全パラメーター表を組み合わせるか、全値入り詳細図を添える。
