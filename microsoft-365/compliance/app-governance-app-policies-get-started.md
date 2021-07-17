---
title: アプリ ポリシーの使用を開始する
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
description: アプリ ポリシーついて説明をします。
ms.openlocfilehash: 3f80048835388e740ba64ac36d1aa19594bf7a9d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420410"
---
# <a name="get-started-with-app-policies"></a>アプリ ポリシーの使用を開始する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

Microsoft アプリ ガバナンスのアプリ ポリシーは、より積極的または事後対応的な条件を実装して、組織内のアプリ コンプライアンスに関する特定のニーズに対するアラートまたは自動修復を作成する方法です。

現在のアプリ ポリシーの一覧を表示するには **[Microsoft 365 コンプライアンス センター] > [アプリ保護とガバナンス] > [ポリシー]** に移動します。

![Microsoft 365 コンプライアンス センターの MAPG ポリシーの概要ページ](..\media\manage-app-protection-governance\mapg-cc-policies.png)

## <a name="whats-available-on-the-app-policies-dashboard"></a>アプリ ポリシー ダッシュボードで使用できる機能

アクティブなポリシー、非アクティブなポリシー、およびテスト ポリシーの数と、ポリシーごとに次の情報を確認できます。

- **ポリシー名**
- **状態**

  - **アクティブ**: すべてのポリシー評価とアクションがアクティブです。
  - **非アクティブ**: すべてのポリシー評価とアクションが無効になっています。
  - **監査モード**: ポリシーの評価は監査モードです。 ポリシーはアクティブですが、ポリシー アクションは無効になっています。

- **重大度**: このポリシーが true として評価されているのでトリガーされたすべてのアラートに設定された重大度レベル。これはポリシーの構成の一部です。
- **アクティブなアラートの数**: ポリシーによって生成された **処理中** または **新しい** 状態のアラート。
- **アラートの合計数**: このポリシーのアクティブなアラートと解決されたアラートの両方。
- **最後のアラートの日付**: このポリシーが原因で最後に生成されたアラートの日付。
- **最終更新日時**: このポリシーが最後に変更された日付。

ポリシーの一覧は、既定で **最終更新日時** の順に並べ替えられます。 リストを別の属性で並べ替えるには、属性名を選択します。

ポリシーを選択すると、次の追加の詳細を含む詳細なポリシー ウィンドウが表示されます。

- **説明**: ポリシーの目的の詳細な説明。
- **作成者**: ポリシーを作成したアカウントのユーザー プリンシパル名 (UPN)。
- このポリシーによって生成されたアクティブなアラートの一覧。

アプリ ポリシーを編集または削除するには、詳細ポリシー ウィンドウで[**編集**] または [**削除**] を選択するか、ポリシー一覧でポリシーの縦方向の省略記号を選択します。

以下のことも実行できます。

- 新しいポリシーの作成。 アプリの使用ポリシーまたはアクセス許可ポリシーから始めることができます。
- ポリシー一覧をコンマ区切り値 (CSV) ファイルにエクスポートします。 たとえば、Microsoft Excel で CSV ファイルを開き、**重大度** と **アラートの合計数** でポリシーを並べ替えることができます。
- ポリシー一覧を検索します。

## <a name="next-step"></a>次の手順

[アプリ ポリシーの作成](app-governance-app-policies-create.md)。