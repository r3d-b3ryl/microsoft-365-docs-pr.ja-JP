---
title: アプリを表示する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: アプリを表示します。
ms.openlocfilehash: 5a11e161fb7b37405b61866599a616874ad4a190
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53623028"
---
# <a name="view-your-apps"></a>アプリを表示する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

Microsoft アプリ ガバナンスを使用すると、テナント内の Microsoft 365 アプリに関する詳細な分析情報をすばやく得ることができます。たとえば、次が表示されます。

- Microsoft Graph API を使用するテナント内の OAuth 対応アプリのリストと、関連するアプリのメタデータおよび使用状況データ。
- リストからアプリを選択することにより詳細な分析情報を備えたアプリの詳細。

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a>テナント内のすべてのアプリのリストを取得する

テナント内のアプリの概要については、**[Microsoft 365 コンプライアンス センター] > [アプリ ガバナンス] > [アプリ]** にアクセスします。

![Microsoft 365 コンプライアンス センターの MAPG アプリの概要ページ](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> アプリ ガバナンス データを表示するには、サインイン アカウントに[これらのロール](app-governance-get-started.md#administrator-roles)のいずれかが必要です。
>

アプリのリストと次の情報が表示されます。

- アプリ名
- 発行元
- M365 認定

  アプリが Microsoft のテクノロジと互換性があり、クラウド アプリのセキュリティのベスト プラクティスに準拠し、Microsoft によってサポートされているかどうかを示します。

- 最終更新日時

  アプリが最後に変更された日付よりも新しい日付の場合、アプリ ガバナンスがクライアントにインストールされた日付を表示します。

- インストール日
- 特権レベル
- ユーザーの数
- データ アクセス

  最終日のテナントでのアプリのデータのアップロードとダウンロードの合計と、前日の変更。

アプリ ガバナンスは、既定では **アプリ名** でアプリ リストを並べ替えます。 リストを別のアプリ属性で並べ替えるには、属性名を選択します。

**[検索]** を選択して、名前でアプリを検索することもできます。

## <a name="getting-detailed-information-on-an-app"></a>アプリの詳細情報を取得する

テナント内の特定のアプリの詳細については、** [Microsoft 365 コンプライアンス センター] > [アプリ ガバナンス] > [アプリ ページ] > *アプリ名*** にアクセスします。

![Microsoft 365 コンプライアンス センターの [アプリ ガバナンス アプリの詳細] ウィンドウ](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

アプリの詳細ウィンドウには、次のタブに関する追加情報が表示されます。

| タブ名 | 説明 |
|:-------|:-----|
| 詳細 | 最初に同意した日付やアプリ ID など、アプリに関する追加データを表示します。 Azure AD に登録されているアプリのプロパティを表示するには、**[Azure AD のアプリを表示]** を選択します。 |
| 使用法 |テナント内のアプリがアクセスするデータを確認し、SharePoint および Exchange リソースのデータ使用量をプロットします。 |
| ユーザー | アプリを使用しているユーザーのリスト、ユーザーが優先アカウントであるかどうか、ダウンロードおよびアップロードされたデータの量を表示します。 |
| アクセス許可 | アプリに付与されて使用されるアクセス許可の概要と、特定のアクセス許可のリストを表示します。 詳細については、「[Microsoft Graph のアクセス許可リファレンス](/graph/permissions-reference)」を参照してください。 |
|||

有効なアプリの場合、選択したアプリの使用を無効にする **[アプリの無効化]** コントロールと、無効にしたアプリの使用を有効にする **[アプリの有効化]** コントロールがあります。これらのアクションには、次の管理者の役割が必要です。

- コンプライアンス管理者
- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター

## <a name="next-step"></a>次の手順

[アプリ全体のコンプライアンスへの取り組みを決定します](app-governance-visibility-insights-compliance-posture.md)。
