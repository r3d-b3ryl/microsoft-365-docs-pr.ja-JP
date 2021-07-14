---
title: 可視性と分析情報について学習する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 可視性と分析情報について学習する。
ms.openlocfilehash: ee485c972193c515bafec55f58a7a89aa1f567f1
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420260"
---
# <a name="learn-about-visibility-and-insights"></a>可視性と分析情報について学習する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

Microsoft アプリ ガバナンスを使用すると、Microsoft 365 アプリケーション エコシステムに関する可視性と意味のある分析情報をすばやく得ることができます。 管理者の注意が必要なテナント内のアラートとアプリの概要を提供するアプリ ガバナンス ダッシュボードから開始します。

アプリ ガバナンスの可視性と分析情報を使用すると、次の情報を確認できます:

- Microsoft Graph API を介して Microsoft 365 データにアクセスする OAuth 対応アプリの一覧です。
- 反応または対応できる豊富なアプリ アクティビティのビュー。

>[!Note]
>Microsoft 365 リソースにアクセスするためのアクセス許可が付与されていない Azure 専用アプリは、アプリ ガバナンスには表示されません。
>

可視性と分析情報に必要な管理者ロールの概要については、「[管理者ロール](app-governance-get-started.md#administrator-roles)」を参照してください。

<!--
From messaging doc, page 21:

View M365 App List & Metadata
View M365 App List of Consented Users
View M365 App Permissions
View M365 App Permission Usage
View Over permissioned Apps
Aggregate M365 API Usage Data by Workload (count, download/upload)
Per-App M365 API Usage Data by Workload (count, download/upload)
Per-User M365 API Usage Data by Workload (count, download/upload)
M365 API Usage Data For High-Value/Classified Assets (count, download/upload)
M365 API Error Analysis per App
-->

アプリ ガバナンスを使用すると、次の情報を確認できます:

- すべての分析情報のダッシュボード。
- ワークロードとユーザー レベルの分析情報を使用して、1 つのアプリとすべてのアプリからアクセスされるデータ。
- アクセス許可、登録日、認定などのアプリケーション情報およびメタデータ。
- 名前、検証状態などの発行元の情報およびメタデータ。
- テナント全体の上位リソース (電子メールとファイル) の使用状況。
- 分析情報:

  - 高い特権を有するアプリ。
  - 過度な特権を有するアプリ。
  - 頻繁に使用されているアプリ。
  - 特定のアプリがアクセスできるデータを持つ上位の同意ユーザー。
  - 特定のアプリがアクセスできるデータを持つ優先度の高いアカウント。

- アプリにアクセスしているユーザーの累積ビュー。
- アラートの分析情報。
- ポリシー リストの分析情報。
<!-->
- アプリ ガバナンス ポータルの MCAS で作成されたポリシー。
-->
- アプリ ガバナンスにおいて、MCAS で生成される OAuth のアラート。

以下のことも実行できます:

- 関連付けられている分析情報をすべて含む 1 つのアプリ (アプリ ページ) にドリルダウンします。
- データ別の上位ユーザーと、1 つのアプリ内の優先度の高いアカウントにドリルダウンします。

## <a name="next-step"></a>次の手順

[アプリケーションの分析情報から始めます。](app-governance-visibility-insights-get-started.md)
