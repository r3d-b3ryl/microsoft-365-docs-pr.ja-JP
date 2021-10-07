---
title: 可視性と分析情報の使用を開始する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: 可視性と分析情報の使用を開始します。
ms.openlocfilehash: fc7a76154437b57876a52cad5de1f637b8da7bc0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201939"
---
# <a name="get-started-with-visibility-and-insights"></a>可視性と分析情報の使用を開始する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

開始する最初の場所は、[https://aka.ms/appgovernance](https://aka.ms/appgovernance) のアプリ ガバナンス ダッシュボードです。 アプリ ガバナンス データを表示するには、サインイン アカウントに[これらのアプリ ガバナンス管理者の役割](app-governance-get-started.md#administrator-roles)のいずれかが必要であることに注意してください。

![Microsoft 365 コンプライアンス センターの [アプリ ガバナンス概要] ページ。](..\media\manage-app-protection-governance\mapg-cc-overview.png)

**[Office 365] > [Microsoft 365 コンプライアンス センター] > [アプリ ガバナンス] > [概要ページ]** からアプリ ガバナンス ダッシュボードにアクセスすることもできます。

## <a name="whats-available-on-the-dashboard"></a>ダッシュボードで使用できる機能

ダッシュボードには、テナント内の Microsoft 365 アプリ エコシステムのコンポーネントの概要が含まれています。

- **テナントの概要**: 主要なアプリとアラートのカテゴリの数。
- **上位のアラート**: テナント内の最新のアクティブなアラート 10 件
- **データとリソースへのアクセス**: グラフの各月の列にマウスでポイントすると、対応する値が表示されます。
  - **過去 4 か月間のデータ アクセス**: 過去 4 か月間に Graph API を通じてテナント内のすべてのアプリがアクセスした合計データを追跡します。現在、メールとファイルのアップロード/ダウンロードの使用状況のみが含まれています。
  - **過去 4 か月間の上位リソース のデータ アクセス**: 過去 4 か月間のデータ使用状況、リソースの種類別に分類されます。現在、メールとファイルのアップロード/ダウンロードの使用状況のみが含まれています
- **アプリの保護とガバナンスの改善**: アプリの使用法やアクセス許可ポリシーの作成など、推奨されるアクション。
- **カテゴリ別の上位アプリ**: 次のカテゴリ別に並べ替えられた上位アプリ:
  
  - **すべてのカテゴリ**: 使用可能なすべてのカテゴリに並べ替えます。
  - **高特権**: 高特権は、プラットフォームの機械学習とシグナルに基づいて内部で決定されたカテゴリです。
  - **特権超過**: アプリ ガバナンスが、アプリケーションに付与されたアクセス許可が過去 90 日間使用されていないことを示すテレメトリを受信すると、そのアプリケーションは特権超過になります。 アプリ ガバナンスは、アプリが特権超過かどうかを判断するために、少なくとも 90 日間稼働している必要があります。  
  - **未確認**: [発行元の認定](/azure/active-directory/develop/publisher-verification-overview)を受けていないアプリケーションは未確認と見なされます。
  - **アプリのみ**: [アプリケーションのアクセス許可](/azure/active-directory/develop/v2-permissions-and-consent#permission-types)は、サインインしているユーザーなしで実行できるアプリに使用します。 テナント全体のデータにアクセスする権限を持つアプリは、潜在的にリスクが高くなります。
  - **新しいアプリ**: 過去 7 日間に登録された新しい Microsoft 365 アプリ。  

## <a name="view-app-insights"></a>アプリの分析情報を表示する

アプリ ガバナンスの主な価値の 1 つは、アプリのアラートと分析情報をすばやく表示する機能です。アプリの分析情報を表示するには:

1. アプリ ガバナンス ポータル ページで、**[Apps]** を選択します。
1. **[分類項目]** ドロップダウン リストを使用して、次のオプションから選択します。
    - すべてのアプリ
    - 高特権
    - 過度な特権
    - 未確認の発行元
    - アプリ専用
    - 新しいアプリ
1. 詳細を表示するアプリの名前を選択します。 アプリ名を選択すると、次の図に示すように、右側に詳細ウィンドウが開きます。

:::image type="content" source="../media/manage-app-protection-governance/app-governance-app-insight.png" alt-text="選択したアプリの詳細ウィンドウを示す画像。":::

> [!NOTE]
> リスト表示されるアプリは、テナントに存在するアプリによって異なります。

クエリを保存すると、定義されたフィルターの一覧を現在のビューに保存できます。 これにより、将来、データのサブセットを選択する時間が節約される可能性があります。

詳細ウィンドウでは、過去 30 日間のアプリの使用状況、アプリに同意したユーザー、アプリに割り当てられたアクセス許可を表示することもできます。 管理者は、アラートを生成しているアプリのアクティビティとアクセス許可を確認し、[詳細] ウィンドウの **[無効にされたアプリ]** ボタンを使用してアプリを無効にすることを決定できます。

## <a name="next-step"></a>次の手順

[特定のアプリに関する詳細な分析情報を取得します](app-governance-visibility-insights-view-apps.md)。
