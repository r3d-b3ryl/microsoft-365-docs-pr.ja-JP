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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: 管理者向けの規範的な手順、ライセンス要件、法的、ビジネス上、または規制上の義務に対して Microsoft 365 で価値の高いコンテンツを管理する一般的なシナリオ。
ms.openlocfilehash: 4a0de19b7630ad89dadb071b80065ff44fde72bb
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67106823"
---
# <a name="get-started-with-records-management"></a>レコード管理の使用を開始する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

Microsoft 365 のレコード管理ソリューションを使用して、組織内の法的事項、ビジネス、または規制上の義務を有する価値の高いコンテンツの管理を開始する準備はできましたか? 開始するには、次のガイダンスを使用してください。

1. Microsoft 365 での **保持と削除の仕組み** を理解し、ドキュメントやメールをアイテム レベルで管理する保持ラベルを補完するためにアイテム保持ポリシーを使用する必要があるかどうかを特定します。[アイテム保持ポリシーと保持ラベルに関する詳細情報](retention.md)
    
    必要に応じて、Microsoft 365 ワークロード全体のデータのベースライン ガバナンスのために[アイテム保持ポリシーを作成](create-retention-policies.md)します。
    
2. **レコード管理ソリューションの理解** と、ドキュメントやメールがレコード宣言される場合にどのように保持ラベルを使用してアクションを許可したり禁止したりするかについて説明します。[レコード管理に関する詳細情報](records-management.md)

3. 既存のプランがある場合はそれをインポートするか、新しい保持ラベルを作成して、**保持および削除の設定とアクション、およびアイテムを記録としてマークするタイミングについて、ファイル プランを作成** します。[ファイル プランを使用して保持ラベルを作成および管理する](file-plan-manager.md)

4. **保持ラベルを発行して適用** します。保持ラベルは複数のポリシーで使用できる再利用可能な文書パーツで、ユーザーのワークフローに組み込むことができます。

    - [アイテム保持ラベルを発行してアプリに適用する](create-apply-retention-labels.md)
    - [保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md)

> [!TIP]
> レコードを Microsoft 365 に移行していて、変更されていないことを検証する必要がある場合は、「[移行されたレコードの検証](records-management.md#validating-migrated-records)」を参照してください。

## <a name="subscription-and-licensing-requirements"></a>サブスクリプションとライセンス要件

レコード管理はさまざまな異なるサブスクリプションに対応しており、ユーザーのライセンス要件は使用する機能によって異なります。

Microsoft Purview 機能のメリットを得られるようにユーザーにライセンスを付与するためのオプションを確認するには、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。 レコード管理については、「[Microsoft Purview データ ライフサイクル管理と Microsoft Purview レコード管理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-data-lifecycle-management--microsoft-purview-records-management)」の、機能レベルのライセンス要件についてのセクションを参照してください。

## <a name="permissions"></a>アクセス許可

レコード管理を担当するコンプライアンス チームのメンバーには、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>へのアクセス許可が必要です。 既定により、テナント管理者 (グローバル管理者) はこの場所にアクセスでき、テナント管理者のすべてのアクセス許可を与えることなく、コンプライアンス責任者やその他のユーザーにアクセス権を付与できます。この制限された管理用にアクセス権を付与するには、[処理確認と検証](disposition.md)など、レコード管理に関するすべての機能に対するアクセス許可を付与する **[レコード管理]** の管理者役割グループにユーザーを追加することをお勧めします。

読み取り専用の役割の場合は、新しい役割グループを作成し、このグループに **閲覧限定レコード管理** の役割を追加することができます。

ユーザーを既定の役割に追加する手順、または独自の役割グループを作成する手順については、「[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md)」を参照してください。

これらの権限は、レコードを宣言し、処理を管理する保持ラベルを作成、構成、適用するためにのみ必要です。 保持ラベルを構成するユーザーは、コンテンツへのアクセスを必要としません。

## <a name="common-scenarios"></a>一般的なシナリオ

次の表は、レコード管理でサポートされているシナリオにビジネス要件をマッピングするのに役立ちます。

> [!TIP]
> 特定の業界規制に準拠する必要がある場合 規制に特化したガイダンスについては、「[データ ライフサイクル管理およびレコード管理の規制要件](retention-regulatory-requirements.md)」を確認してください。

|必要な作業...|ドキュメント|
|----------------|---------------|
|レコードを宣言する |[保持ラベルを使用してレコードを宣言する](declare-records.md)|
|レコードを更新する |[SharePoint または OneDrive に保存されているレコードを更新するためにレコードのバージョン管理を使用する](record-versioning.md)|
|管理者とユーザーが、以下でドキュメントと電子メールの保持および削除アクションを手動で適用できるようにする <br />-  SharePoint <br />- OneDrive <br />- Outlook および Outlook on the web|[アイテム保持ラベルを発行してアプリに適用する](create-apply-retention-labels.md)|
|サイト管理者が、SharePoint ライブラリ、フォルダー、またはドキュメントセット内のすべてのコンテンツの既定の保持および削除アクションを設定できるようにする|[アイテム保持ラベルを発行してアプリに適用する](create-apply-retention-labels.md)|
|Outlook のルールを使用して、ユーザーが電子メールの保持および削除アクションを自動的に適用できるようにする|[アイテム保持ラベルを発行してアプリに適用する](create-apply-retention-labels.md)|
|管理者が保持アクションと削除アクションをドキュメント理解モデルに適用できるようにして、SharePoint ライブラリで識別されたドキュメントにこれらが自動的に適用されるようにします。|[アイテム保持ラベルを発行してアプリに適用する](create-apply-retention-labels.md)|
|ドキュメントと電子メールに保持および削除アクションを自動的に適用する |[保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md)|
|次のようなイベントが発生したときに保持期間を開始する  <br />- 従業員が退職する <br />- 契約満了 <br />- 製品の有効期間の終了| [イベントの発生時に保持を開始する](event-driven-retention.md)|
|ポリシーの変更を制限して規制要件を満たす、または不正な管理者から保護する| [保管ロックを使用して、アイテム保持ポリシーと保持ラベル ポリシーへの変更を制限する](retention-preservation-lock.md)
|SharePoint で各種ドキュメントのライフサイクルを管理する| [保持ラベルを使用して、SharePoint に保存されているドキュメントのライフサイクルを管理する](auto-apply-retention-labels-scenario.md)|
|個人データを含むコンテンツが保存されつつあるか、または長期間そのままに放置された状態であるというアラートを受け取ったときに、ファイルに保持ラベルを適用する| [プライバシー リスク管理のアラートを調査して修復します](/privacy/priva/risk-management-alerts)|
|保持期間の終了時にコンテンツが削除される前に、誰かがレビューと承認を行うようにする|[廃棄確認](disposition.md#disposition-reviews) |
|保存期間の終了時に完全に削除されたコンテンツの廃棄の証拠を取得する|[レコードの廃棄](disposition.md#disposition-of-records) |
| 保持および削除設定がアイテムに適用される方法と場所を監視する | [保持ラベルの監視](retention.md#monitoring-retention-labels) |
| 保持ラベル、イベント ベースの保持をプログラムで作成および管理し、レコード管理の反復タスクを自動化する | [レコード管理の Microsoft Graph API (プレビュー)](compliance-extensibility.md#microsoft-graph-api-for-records-management-preview) |

## <a name="end-user-documentation"></a>エンド ユーザー向けのドキュメント

ベースライン データ ガバナンスにアイテム保持ポリシーを使用している場合、通常、ユーザーが操作することなくバックグラウンドで目立たずに動作します。 そのため、ユーザーへの説明はほとんど必要ありません。 Teams のアイテム保持ポリシーは、メッセージが削除されたときに、[アイテム保持ポリシーに関する Teams メッセージ](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)へのリンクとともにユーザーに通知します。

一方、保持ラベルは Microsoft 365 アプリに UI が存在するため、これらのラベルを運用ネットワークに展開する前に、エンドユーザーとヘルプ デスクにガイダンスを提供するようにしてください。 ユーザーが SharePoint および OneDrive、および編集用のレコードのロック解除に関する情報で保持ラベルを適用できるようにするには、「[SharePoint または OneDrive のファイルに保持ラベルを適用する](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df)」を参照してください。

ただし、最も効果的なエンド ユーザー向けのドキュメントは、選択した保持ラベル名と構成に関するカスタマイズされたガイダンスと手順です。 次のページを表示して、ユーザーのトレーニングに使用できるアイテムをダウンロードします。[アイテム保持ラベルのエンド ユーザー トレーニング](https://microsoft.github.io/ComplianceCxE/enduser/retention/)。