---
title: 攻撃表面の縮小ルールの展開フェーズ 3 - 実装
description: 攻撃表面の縮小ルールの展開を実装するためのガイダンスを提供します。
keywords: 攻撃表面の縮小ルールの展開、ASR の展開、asr ルールの有効化、ASR の構成、ホスト侵入防止システム、保護ルール、悪用防止ルール、感染防止ルール、Microsoft Defender for Endpoint、CONFIGURE ASR ルール
search.product: eADQiWindows 10XVcnh
ms.reviewer: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 8489e31f0178fb4c0ab8e5159a71bc0691276689
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171754"
---
# <a name="attack-surface-reduction-rules-deployment-phase-3-implement"></a>攻撃表面の縮小ルールの展開フェーズ 3: 実装

実装フェーズでは、リングをテストから機能状態に移動します。

> [!div class="mx-imgBorder"]
> ![ASR ルールの実装手順](images/asr-rules-implementation-steps.png)

## <a name="step-1-transition-asr-rules-from-audit-to-block"></a>手順 1: 監査からブロックへの ASR ルールの移行

1. 監査モードですべての除外が決定された後、トリガーされるイベントが最も少ないルールから始め、一部の ASR ルールを "ブロック" モードに設定します。 「攻撃表面 [の縮小ルールを有効にする」を参照してください](enable-attack-surface-reduction.md)。
2. ポータルのレポート ページを確認Microsoft 365 Defender Microsoft Defender for Endpoint の脅威[保護レポートを参照してください](threat-protection-reports.md)。 ASR チャンピオンからのフィードバックも確認します。
3. 必要に応じて除外を絞り込むか、新しい除外を作成します。
4. 問題のあるルールを [監査] に切り替えます。

  >[!Note]
  >問題のあるルール (ノイズが多すぎるルール) の場合は、ルールをオフにするか、監査に戻すよりも除外を作成する方が良いです。 環境に最適な情報を判断する必要があります。

  >[!Tip]
  >使用可能な場合は、ルールの [警告モード] 設定を利用して中断を制限します。 警告モードで ASR ルールを有効にすると、トリガーされたイベントをキャプチャし、エンド ユーザー アクセスを実際にブロックすることなく、中断の可能性を確認できます。 詳細については、「 [ユーザーの警告モード」を参照してください](attack-surface-reduction.md#warn-mode-for-users)。

### <a name="how-does-warn-mode-work"></a>警告モードの動作方法

警告モードは、実質的には Block 命令ですが、ユーザーが特定のフローまたはアプリの後続の実行を "ブロック解除" するオプションを使用します。 デバイス、ユーザー、ファイル、プロセスの組み合わせごとに警告モードのブロックを解除します。 警告モードの情報はローカルに保存され、期間は 24 時間です。

### <a name="step-2-expand-deployment-to-ring-n--1"></a>手順 2: 展開をリング n + 1 に展開する

リング 1 の ASR ルールが正しく構成されていることを確信している場合は、展開の範囲を次のリング (リング n + 1) に拡大できます。

展開プロセスである手順 1 ~ 3 は、以降のリングごとに基本的に同じです。

1. 監査のテスト ルール
2. ASR がトリガーした監査イベントをポータルでMicrosoft 365 Defenderする
3. 除外を作成する
4. レビュー: 必要に応じて除外を絞り込み、追加、または削除する
5. ルールを "ブロック" に設定する
6. ポータルのレポート ページMicrosoft 365 Defenderします。
7. 除外を作成します。
8. 問題のあるルールを無効にするか、監査に戻します。

## <a name="additional-topics-in-this-deployment-collection"></a>この展開コレクションのその他のトピック

[攻撃表面の縮小ルールの展開ガイド - 概要](attack-surface-reduction-rules-deployment.md)

[攻撃表面の縮小ルールの展開フェーズ 1 - 計画](attack-surface-reduction-rules-deployment-phase-1.md)

[攻撃表面の縮小ルールの展開フェーズ 2 - test](attack-surface-reduction-rules-deployment-phase-2.md)

[攻撃表面の縮小ルールの展開フェーズ 4 - 運用](attack-surface-reduction-rules-deployment-phase-4.md)
