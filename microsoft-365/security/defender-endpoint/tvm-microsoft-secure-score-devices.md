---
title: デバイスの Microsoft セキュア スコア
description: デバイスのスコアは、アプリケーション、オペレーティング システム、ネットワーク、アカウント、およびセキュリティ制御全体にわたるデバイスの集合的なセキュリティ構成状態を示します。
keywords: Microsoft Secure Score for Devices, Microsoft Defender for Endpoint Microsoft Secure Score for Devices, secure score, configuration score, 脅威と脆弱性の管理, security controls, improvement opportunities, security configuration score over time, security posture, baseline
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
ms.openlocfilehash: 1d63e240c0698273807421a4121061630b8f3951
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64499531"
---
# <a name="microsoft-secure-score-for-devices"></a>デバイスの Microsoft セキュア スコア

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

> [!NOTE]
> 構成スコアは、デバイスの Microsoft Secure Score として脅威と脆弱性の管理の一部になりました。

デバイスのスコアは、Microsoft 365 Defender ポータルの[脅威と脆弱性の管理 ダッシュボード](tvm-dashboard-insights.md)に表示されます。 デバイスの Microsoft セキュア スコアが高いということは、エンドポイントがサイバー セキュリティの脅威攻撃に対してより回復力があることを意味します。 次のカテゴリのデバイスの集合的なセキュリティ構成状態が反映されます。

- アプリケーション
- オペレーティング システム
- ネットワーク
- アカウント
- セキュリティ コントロール

カテゴリを選択して [ [**セキュリティの推奨事項**](tvm-security-recommendation.md) ] ページに移動し、関連する推奨事項を表示します。

## <a name="how-it-works"></a>メカニズム

> [!NOTE]
> デバイスの Microsoft Secure Score は、現在、グループ ポリシーを介して設定された構成をサポートしています。 現在の部分的なIntuneのサポートにより、Intuneを通じて設定された構成が正しく構成されていないと表示される場合があります。 組織がセキュリティで保護された構成管理にIntuneを使用している場合は、IT 管理者に問い合わせて実際の構成状態を確認してください。

Microsoft Secure Score for Devices カードのデータは、慎重で継続的な脆弱性検出プロセスの結果です。 これは、継続的に次の構成検出評価で集計されます。

- 収集された構成を収集されたベンチマークと比較して、正しく構成されていない資産を検出する
- 修復または部分的に修復できる脆弱性に構成をマップする (リスク削減)
- ベスト プラクティスの構成ベンチマーク (ベンダー、セキュリティ フィード、内部調査チーム) を収集して管理する
- すべての資産からセキュリティ制御構成状態の変更を収集して監視する

## <a name="improve-your-security-configuration"></a>セキュリティ構成を改善する

セキュリティに関する推奨事項の一覧から問題を修復することで、セキュリティ構成を改善します。 そうすることで、Microsoft Secure Score for Devices が向上し、組織はサイバーセキュリティの脅威や脆弱性に対する回復力を高めます。

1. 脅威と脆弱性の管理 ダッシュボードの Microsoft Secure Score for Devices カードから、いずれかのカテゴリを選択します。 そのカテゴリに関連する推奨事項の一覧が表示されます。 [**[セキュリティに関する推奨事項**](tvm-security-recommendation.md)] ページに移動します。 すべてのセキュリティに関する推奨事項を表示する場合は、[セキュリティに関する推奨事項] ページに移動したら、検索フィールドをクリアします。

2. リストでアイテムを選択します。 ポップアップ パネルが開き、推奨事項に関連する詳細が表示されます。 **[修復オプション] を選択します**。

   :::image type="content" source="images/security-controls.png" alt-text="セキュリティ コントロールに関連するセキュリティに関する推奨事項" lightbox="images/security-controls.png":::

3. 説明を読んで、問題のコンテキストと次に実行する操作を理解してください。 期限を選択し、メモを追加し、[ **すべての修復アクティビティ データを CSV にエクスポート** する] を選択して、フォローアップのためにメールに添付できるようにします。

4. **要求を送信します**。 修復タスクが作成されたことを示す確認メッセージが表示されます。

   :::image type="content" source="images/remediation-task-created.png" alt-text="修復タスクの作成の確認" lightbox="images/remediation-task-created.png":::

5. CSV ファイルを保存します。

   :::image type="content" source="images/tvm_save_csv_file.png" alt-text="CSV ファイルを保存するオプションを含むページ" lightbox="images/tvm_save_csv_file.png":::

6. IT 管理者にフォローアップ メールを送信し、修復に割り当てた時間がシステムに反映されるようにします。

7. ダッシュボードで **、Microsoft Secure Score for Devices** カードをもう一度確認します。 セキュリティ制御に関する推奨事項の数が減ります。 **[セキュリティの** 推奨事項] ページに戻るために [**セキュリティ** コントロール] を選択すると、対処した項目は表示されなくなります。 Microsoft Secure Score for Devices は増加する必要があります。

> [!IMPORTANT]
>脆弱性評価の検出率を高めるには、次の必須のセキュリティ更新プログラムをダウンロードし、ネットワークに展開します。
>
> - 19H1 のお客様| [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)
> - RS5 のお客様| [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> - RS4 のお客様| [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> - RS3 のお客様| [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
>
> セキュリティ更新プログラムをダウンロードするには:
>
> 1. [Microsoft Update カタログ](https://www.catalog.update.microsoft.com/home.aspx)に移動します。
> 2. ダウンロードする必要があるセキュリティ更新プログラムの KB 番号をキー入力し、[ **検索**] をクリックします。

## <a name="related-topics"></a>関連項目

- [脅威と脆弱性の管理の概要](next-gen-threat-and-vuln-mgt.md)
- [ダッシュボード](tvm-dashboard-insights.md)
- [暴露スコア](tvm-exposure-score.md)
- [セキュリティに関する推奨事項](tvm-security-recommendation.md)
