---
title: Microsoft 365 でレコード管理の使用を開始する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 法的事項、ビジネス、または規制上の義務を有する価値の高いコンテンツを管理する、Microsoft 365 向けのレコード管理ソリューションが必要であるのに、どこから開始すればいいかわからなくなっていませんか? 開始するのに役立つ実用的なガイダンスをご覧ください。
ms.openlocfilehash: 0af5391a7964e242067d70e559d082ede0c9fb3a
ms.sourcegitcommit: 584445b62cb82218597b62495fb76fcb5b12af9d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59497773"
---
# <a name="get-started-with-records-management"></a>レコード管理の使用を開始する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

Microsoft 365 のレコード管理ソリューションを使用して、組織内の法的事項、ビジネス、または規制上の義務を有する価値の高いコンテンツの管理を開始する準備はできましたか? 開始するには、次のガイダンスを使用してください。

1. **レコード管理ソリューションの理解** と、ドキュメントやメールがレコード宣言される場合にどのようなアクションが許可されたり禁止されたりするかについて説明します。[レコード管理に関する詳細情報](records-management.md)。

2. 保持ラベルはレコード宣言に使用されるため、SharePoint および Exchange 向けの **アイテム保持レベルや保持の機能を理解してください**。[保持ポリシーおよび保持ラベルに関する詳細情報](retention.md)

3. 既存のプランをお持ちの場合は、[既存のプランをインポート](file-plan-manager.md#import-retention-labels-into-your-file-plan)することで **保持設定およびアクションのためのファイルプランを作成** するか、[レコード宣言する新しい保持ラベル](declare-records.md)を作成します。

4. **保持ラベルを発行して適用** します。 保持ラベルは複数のポリシーで使用できる再利用可能な文書パーツで、ユーザーのワークフローに組み込むことができます。

    - [アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)
    - [保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md)

## <a name="subscription-and-licensing-requirements-for-records-management"></a>レコード管理のサブスクリプションおよびライセンス要件

レコード管理はさまざまな異なるサブスクリプションに対応しており、ユーザーのライセンス要件は使用する機能によって異なります。

Microsoft 365 コンプライアンス機能のメリットを得られるようにユーザーにライセンスを付与するためのオプションを確認するには、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。 レコード管理については、「[レコード管理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management)」セクション、および機能レベルのライセンス要件に関する PDF ダウンロード ファイルを参照してください。

## <a name="permissions-required-for-records-management"></a>レコード管理に必要なアクセス許可

レコード管理を担当するコンプライアンス チームのメンバーには、[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)へのアクセス許可が必要です。 既定により、テナント管理者 (グローバル管理者) はこの場所にアクセスでき、テナント管理者のすべてのアクセス許可を与えることなく、コンプライアンス責任者やその他のユーザーにアクセス権を付与できます。この制限された管理用にアクセス権を付与するには、[処理確認と検証](disposition.md)など、レコード管理に関するすべての機能に対するアクセス許可を付与する **[レコード管理]** の管理者役割グループにユーザーを追加することをお勧めします。

読み取り専用の役割の場合は、新しい役割グループを作成し、このグループに **閲覧限定レコード管理** の役割を追加することができます。

ユーザーを既定の役割に追加する手順、または独自の役割グループを作成する手順については、「[Microsoft 365 コンプライアンス センターのアクセス許可](microsoft-365-compliance-center-permissions.md)」を参照してください。

これらの権限は、レコードを宣言し、処理を管理する保持ラベルを作成、構成、適用するためにのみ必要です。 保持ラベルを構成するユーザーは、コンテンツへのアクセスを必要としません。

## <a name="common-scenarios-for-records-management"></a>レコード管理の一般的なシナリオ

次の表は、レコード管理でサポートされているシナリオにビジネス要件をマッピングするのに役立ちます。

> [!NOTE]
> レコード管理では、アイテム保持ラベルを使用してアイテムをレコードとしてマークするため、この表にある多くのシナリオは、[アイテム保持ポリシーと保持ラベルの一般的なシナリオ](get-started-with-retention.md#common-scenarios-for-retention-policies-and-retention-labels)としても表示されます。

|必要な作業...|ドキュメント|
|----------------|---------------|
|レコードを宣言する |[保持ラベルを使用してレコードを宣言する](declare-records.md)|
|レコードを更新する |[SharePoint または OneDrive に保存されているレコードを更新するためにレコードのバージョン管理を使用する](record-versioning.md)|
|管理者とユーザーが、以下でドキュメントと電子メールの保持および削除アクションを手動で適用できるようにする <br />-  SharePoint <br />- OneDrive <br />- Outlook および Outlook on the web|[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)|
|サイト管理者が、SharePoint ライブラリ、フォルダー、またはドキュメントセット内のすべてのコンテンツの既定の保持および削除アクションを設定できるようにする|[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)|
|Outlook のルールを使用して、ユーザーが電子メールの保持および削除アクションを自動的に適用できるようにする|[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)|
|管理者が保持アクションと削除アクションをドキュメント理解モデルに適用できるようにして、SharePoint ライブラリで識別されたドキュメントにこれらが自動的に適用されるようにします。|[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)|
|ドキュメントと電子メールに保持および削除アクションを自動的に適用する |[保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md)|
|次のようなイベントが発生したときに保持期間を開始する  <br />- 従業員が退職する <br />- 契約満了 <br />- 製品の有効期間の終了| [イベントの発生時に保持を開始する](event-driven-retention.md)|
|ポリシーの変更を制限して規制要件を満たす、または不正な管理者から保護する| [保管ロックを使用して、アイテム保持ポリシーと保持ラベル ポリシーへの変更を制限する](retention-preservation-lock.md)
|SharePoint で各種ドキュメントのライフサイクルを管理する| [保持ラベルを使用して、SharePoint に保存されているドキュメントのライフサイクルを管理する](auto-apply-retention-labels-scenario.md)|
|保持期間の終了時にコンテンツが削除される前に、誰かがレビューと承認を行うようにする|[廃棄確認](disposition.md#disposition-reviews) |
|保存期間の終了時に完全に削除されたコンテンツの廃棄の証拠を取得する|[レコードの廃棄](disposition.md#disposition-of-records) |
| 保持および削除設定がアイテムに適用される方法と場所を監視する | [保持ラベルの監視](retention.md#monitoring-retention-labels) |

## <a name="end-user-documentation-for-records"></a>レコードに関するエンド ユーザー向けのドキュメント

レコード管理に使用される保持ラベルは、Microsoft 365 アプリに UI が存在します。保持ラベルを運用ネットワークに展開する前に、エンド ユーザーとヘルプ デスクにガイダンスを提供するようにしてください。

ユーザーが SharePoint および OneDrive で保持ラベルを適用できるようにするには、編集用のレコードのロック解除に関する情報が含まれている、「[SharePoint または OneDrive のファイルに保持ラベルを適用する](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df)」を参照してください。

ただし、最も効果的なエンド ユーザー向けのドキュメントは、選択した保持ラベル名と構成に関するカスタマイズされたガイダンスと手順です。 ユーザーのトレーニングと導入の促進に使用できるダウンロード パッケージについては、次のブログ記事を参照してください: [M365 の保持ラベルのエンド ユーザー トレーニング – 導入を加速する方法](https://techcommunity.microsoft.com/t5/microsoft-security-and/end-user-training-for-retention-labels-in-m365-how-to-accelerate/ba-p/1750861)。
