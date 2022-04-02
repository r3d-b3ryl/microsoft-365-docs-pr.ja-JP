---
title: デバイス向けの Microsoft セキュア スコア
description: デバイスのスコアは、アプリケーション、オペレーティング システム、ネットワーク、アカウント、およびセキュリティ制御全体にわたるデバイスの一括セキュリティ構成状態を示します。
keywords: Microsoft Secure Score for Devices, Microsoft Defender for Endpoint Microsoft Secure Score for Devices, secure score, configuration score, 脅威と脆弱性の管理, security controls, improvement opportunitis, security configuration score over time, security configuration score, baseline
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 97ce614a77b85ae6e22e771a413ae5bce51abce7
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465797"
---
# <a name="microsoft-secure-score-for-devices"></a>デバイス向けの Microsoft セキュア スコア

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

> [!NOTE]
> 構成スコアは、Microsoft Secure Score 脅威と脆弱性の管理デバイスの一部になります。

デバイスのスコアは、ポータルの脅威と脆弱性の管理[ダッシュボード](tvm-dashboard-insights.md)にMicrosoft 365 Defenderされます。 デバイスの Microsoft セキュア スコアが高いということは、エンドポイントがサイバー セキュリティの脅威攻撃に対してより回復力があることを意味します。 これは、次のカテゴリにわたるデバイスの一括セキュリティ構成状態を反映します。

- アプリケーション
- オペレーティング システム
- ネットワーク
- アカウント
- セキュリティ コントロール

カテゴリを選択して、[セキュリティの推奨事項 [**] ページに移動**](tvm-security-recommendation.md) し、関連する推奨事項を表示します。

## <a name="turn-on-the-microsoft-secure-score-connector"></a>Microsoft Secure Score コネクタを有効にする

Microsoft Defender for Endpoint シグナルを転送し、Microsoft Secure Score をデバイスのセキュリティ状態に可視化します。 転送されたデータは、Microsoft Secure Score データと同じ場所に保存および処理されます。

変更は、ダッシュボードに反映するために数時間かかる場合があります。

1. ナビゲーション ウィンドウで、[**エンドポイントの**\>全般設定 **機能]** \> **に** \> **移動します。**

2. 下にスクロールして **Microsoft Secure Score に移動** し、設定を [オン] に切り **替える**。

3. **[環境設定の保存]** を選択します。

## <a name="how-it-works"></a>しくみ

> [!NOTE]
> Microsoft Secure Score for Devices は現在、グループ ポリシーを介して設定された構成をサポートしています。 現在の部分的な Intune のサポートにより、Intune を介して設定されている可能性がある構成が正しく構成されていないと表示される場合があります。 組織が安全な構成管理のために Intune を使用している場合に、IT 管理者に問い合わせて実際の構成状態を確認します。

Microsoft Secure Score for Devices カードのデータは、細心の注意を払い、継続的な脆弱性検出プロセスの製品です。 次の構成検出評価が継続的に集計されます。

- 収集された構成と収集されたベンチマークを比較して、構成が誤ったアセットを検出する
- 構成を修正または部分的に修復できる脆弱性にマップする (リスクの軽減)
- ベスト プラクティス構成ベンチマーク (ベンダー、セキュリティ フィード、内部調査チーム) を収集して維持する
- すべてのアセットからセキュリティ制御構成状態の変更を収集および監視する

## <a name="improve-your-security-configuration"></a>セキュリティ構成の改善

セキュリティの推奨事項の一覧から問題を修復して、セキュリティ構成を改善します。 そうすると、Microsoft Secure Score for Devices が向上し、組織はサイバーセキュリティの脅威や脆弱性に対してより回復力が高くなります。

1. ダッシュボードの Microsoft Secure Score for Devices カード脅威と脆弱性の管理、カテゴリの 1 つを選択します。 そのカテゴリに関連する推奨事項の一覧が表示されます。 [セキュリティの推奨事項] [**ページに移動**](tvm-security-recommendation.md) します。 すべてのセキュリティ推奨事項を表示する場合は、[セキュリティの推奨事項] ページに移動したら、検索フィールドをクリアします。

2. リストでアイテムを選択します。 フライアウト パネルが開き、推奨事項に関連する詳細が表示されます。 [ **修復オプション] を選択します**。

   :::image type="content" source="images/security-controls.png" alt-text="セキュリティコントロールに関連するセキュリティの推奨事項" lightbox="images/security-controls.png":::

3. 説明を読んで、問題のコンテキストと次に何を行うのかを理解します。 期日を選択し、メモを追加し、[すべての修復アクティビティ データを **CSV** にエクスポートする] を選択して、フォローアップのためにメールに添付できます。

4. **要求を送信します**。 修復タスクが作成されたという確認メッセージが表示されます。

   :::image type="content" source="images/remediation-task-created.png" alt-text="修復タスクの作成確認" lightbox="images/remediation-task-created.png":::

5. CSV ファイルを保存します。

   :::image type="content" source="images/tvm_save_csv_file.png" alt-text="CSV ファイルを保存するオプションを含むページ" lightbox="images/tvm_save_csv_file.png":::

6. IT 管理者にフォローアップ メールを送信し、修復がシステムに伝達される時間を許可します。

7. ダッシュボードで **Microsoft Secure Score for Devices** カードを再度確認します。 セキュリティ制御の推奨事項の数は減少します。 [セキュリティの **推奨事項]** ページに戻る [セキュリティ コントロール] を選択すると、アドレス指定したアイテムは表示されません。 Microsoft Secure Score for Devices は増加する必要があります。

> [!IMPORTANT]
>脆弱性評価の検出率を上げるには、次の必須のセキュリティ更新プログラムをダウンロードし、ネットワークに展開します。
>
> - 19H1 のお客様| [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)
> - RS5 のお客様| [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> - RS4 のお客様| [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> - RS3 のお客様| [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
>
> セキュリティ更新プログラムをダウンロードするには、次の方法を実行します。
>
> 1. [Microsoft [Update Catalog] に移動します](https://www.catalog.update.microsoft.com/home.aspx)。
> 2. ダウンロードする必要があるセキュリティ更新プログラムの KB 番号をキーインし、[検索] をクリック **します**。

## <a name="related-topics"></a>関連項目

- [脅威と脆弱性の管理概要](next-gen-threat-and-vuln-mgt.md)
- [ダッシュボード](tvm-dashboard-insights.md)
- [暴露スコア](tvm-exposure-score.md)
- [セキュリティ上の推奨事項](tvm-security-recommendation.md)
