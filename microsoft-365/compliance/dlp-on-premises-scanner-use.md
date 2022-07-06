---
title: データ損失防止のオンプレミス スキャナーを使用する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: オンプレミスのスキャナーでデータ損失防止を使用して、保存されているデータをスキャンし、オンプレミスのファイル共有とオンプレミスの SharePoint フォルダーとドキュメント ライブラリに保護アクションを実装する方法について説明します。
ms.openlocfilehash: ae5ffce9e664ada6e7476bb02b40f4a5c279d441
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66624181"
---
# <a name="use-the-data-loss-prevention-on-premises-scanner"></a>データ損失防止のオンプレミス スキャナーを使用する

Microsoft Purview データ損失防止オンプレミス機能、および DLP ポリシーで表示される方法を把握するために、いくつかのシナリオをまとめてましたので、確認してください。

> [!IMPORTANT]
> これらの DLP オンプレミス シナリオは、DLP ポリシーの作成と調整に関する公式な手順ではありません。 一般的な状況で DLP ポリシーを使用する必要がある場合は、次のトピックを参照してください。
>
> - [データ損失防止について](dlp-learn-about-dlp.md)
> - [DLP の既定ポリシーの概要](get-started-with-the-default-dlp-policy.md)
> - [テンプレートから DLP ポリシーを作成する](create-a-dlp-policy-from-a-template.md)
> - [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a>シナリオ: DLP ルールに一致するファイルを検出する

DLP オンプレミス スキャナーのデータが複数の領域に表示される

#### <a name="activity-explorer"></a>アクティビティ エクスプローラー

 オンプレミス用の Microsoft DLP は、DLP ルールの一致を検出し、「[アクティビティ エクスプローラー](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer)」に報告します。

#### <a name="microsoft-365-audit-log"></a>Microsoft 365 監査ログ

DLP ルールの一致は、監査ログ UI で利用できます。「[Microsoft Purview コンプライアンス ポータルで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)」をご覧になるか、または [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell からアクセスできます。

#### <a name="aip"></a>AIP

検出データは、以下の場所に保存されている csv 形式のローカル レポートで利用できます。 

**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.

 次の列を調べてください。

- DLP モード
- DLP の状態
- DLP コメント
- DLP ルール名
- DLP アクション
- 所有者
- 現在の NTFS アクセス許可 (SDDL)
- 適用済みの NTFS アクセス許可 (SDDL)
- NTFS アクセス許可の種類

### <a name="scenario-enforce-dlp-rule"></a>シナリオ: DLP ルールを適用する

スキャンしたファイルに DLP ルールを適用する場合、AIP のコンテンツ スキャン ジョブと DLP のポリシー レベルの両方で、適用を有効にする必要があります。

#### <a name="configure-dlp-to-enforce-policy-actions"></a>ポリシー アクションを適用するために DLP を構成する

1. [[データ損失防止](https://compliance.microsoft.com/datalossprevention?viewid=policies)] ページを開き、AIP で構成したオンプレミスの場所リポジトリを対象とする DLP ポリシーを選択します。
2. ポリシーを編集します。
3. 「**ポリシーをテストまたは有効にする**」のページで、**[はい] を選び、ポリシーを今すぐ有効にします**。

## <a name="see-also"></a>関連項目

- [DLP オンプレミス スキャナーの詳細情報](dlp-on-premises-scanner-learn.md)
- [DLP オンプレミス スキャナーの使用を開始する](dlp-on-premises-scanner-get-started.md)
- [データ損失防止について](dlp-learn-about-dlp.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)
