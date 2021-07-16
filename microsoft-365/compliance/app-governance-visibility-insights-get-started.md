---
title: 可視性と分析情報の使用を開始する
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
description: 可視性と分析情報の使用を開始します。
ms.openlocfilehash: 93be3557c32345e81c7126b669ead8edf8ebac21
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430482"
---
# <a name="get-started-with-visibility-and-insights"></a>可視性と分析情報の使用を開始する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

開始する最初の場所は、[https://aka.ms/appgovernance](https://aka.ms/appgovernance) のアプリ ガバナンス ダッシュボードです。 アプリ ガバナンス データを表示するには、サインイン アカウントに[これらのアプリ ガバナンス管理者の役割](app-governance-get-started.md#administrator-roles)のいずれかが必要であることに注意してください。

![Microsoft 365 コンプライアンス センターの [アプリ ガバナンス概要] ページ](..\media\manage-app-protection-governance\mapg-cc-overview.png)

**[Microsoft 365 管理センター] > [Microsoft 365 コンプライアンス センター] > [アプリ ガバナンス] > [概要ページ]** からアプリ ガバナンス ダッシュボードにアクセスすることもできます。

## <a name="whats-available-on-the-dashboard"></a>ダッシュボードで使用できる機能

ダッシュボードには、テナント内の Microsoft 365 アプリ エコシステムのコンポーネントの概要が含まれています。

- **テナントの概要**: 主要なアプリとアラートのカテゴリの数。
- **検出およびポリシー アラート**: テナント内の最新のアクティブなアラート
- **データとリソースへのアクセス**: アプリケーション API アクセスと、テナント内の上位リソースの全体的な使用状況を集約します。 グラフの各月の列にマウスでポイントすると、対応する値が表示されます。
- **アプリの保護とガバナンスの改善**: アプリの使用法やアクセス許可ポリシーの作成など、推奨されるアクション。
- **カテゴリ別の上位アプリ**: 次のカテゴリ別に並べ替えられた上位アプリ:
  
  - **すべてのカテゴリ**: 使用可能なすべてのカテゴリに並べ替えます。
  - **高特権**: 高特権は、プラットフォームの機械学習とシグナルに基づいて内部で決定されたカテゴリです。
  - **特権超過**: アプリ ガバナンスが、アプリケーションに付与されたアクセス許可が過去 90 日間使用されていないことを示すテレメトリを受信すると、そのアプリケーションは特権超過になります。 アプリ ガバナンスは、アプリが特権超過かどうかを判断するために、少なくとも 90 日間稼働している必要があります。  
  - **未確認**: [発行元の認定](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview)を受けていないアプリケーションは未確認と見なされます。
  - **アプリのみ**: [アプリケーションのアクセス許可](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types)は、サインインしているユーザーなしで実行できるアプリに使用します。 テナント全体のデータにアクセスする権限を持つアプリは、潜在的にリスクが高くなります。
  - **新しいアプリ**: 過去 7 日間に登録された新しい Microsoft 365 アプリ。  

## <a name="next-step"></a>次の手順

[特定のアプリに関する詳細な分析情報を取得します](app-governance-visibility-insights-view-apps.md)。
