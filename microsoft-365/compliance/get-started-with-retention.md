---
title: アイテム保持ポリシーと保持ラベルの使用を開始する
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
description: アイテム保持ポリシーと保持ラベルを実装して組織のデータを管理しようと思っても、どこから始めればよいかかわりませんか? 開始するのに役立つ実用的なガイダンスをご覧ください。
ms.openlocfilehash: cc504468611d4a2a2758ef7d52b965c177999217
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198942"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルの使用を開始する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

保持する必要のあるコンテンツを保持し、その必要のないコンテンツを削除することにより、組織のデータの管理を開始する用意はできていますか? 開始するために、次の概要ガイダンスを参考にできます。

1. Microsoft 365 の**保持のしくみを理解**し、アイテム保持ポリシーと保持ラベルのどちらを使用するか、または組み合わせて使用するかを決定します。[保持の詳細](retention.md)に関する記事を参照してください。

2. 組織のポリシーや業界の規制で必要とされている**保持設定とアクションを特定**します。
    
    この評価の一環として、[レコード管理](records-management.md)を使用するかどうかを決定します。

3. 特定した保持設定とアクションに基づいて、**アイテム保持ポリシーと保持ラベルを作成**します。
    
    保持ラベルを使用する場合、[ファイル プラン](file-plan-manager.md)を使用して、スプレッドシートで保持ラベルを定義して微調整することが役立つ場合があります。 その場合は、スプレッドシートをインポートしてラベルを作成します。
    
3. **保持ラベルを発行して適用**します。 アイテム保持ポリシーは "一度設定したらそのまま" の構成を想定して設計されています。一方、保持ラベルは複数のポリシーで使用できる再利用可能な文書パーツで、ユーザーのワークフローに組み込むことができます。 保持ラベルの使用方法については、[一般的なシナリオ](#common-scenarios-for-retention-policies-and-retention-labels)の一覧を参照してください。 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルのサブスクリプションおよびライセンス要件

アイテム保持ポリシーと保持ラベルはさまざまなサブスクリプションでサポートされており、ユーザーのライセンス要件は使用する機能によって異なります。

Microsoft 365 コンプライアンス機能のメリットを得られるようにユーザーにライセンスを付与するためのオプションを確認するには、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)」を参照してください。 保持については、「[情報ガバナンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)」セクション、および機能レベルのライセンス要件に関する PDF または Excel ダウンロード ファイルを参照してください。

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルを作成して管理するために必要なアクセス許可

アイテム保持ポリシーと保持ラベルを作成して管理するコンプライアンス チームのメンバーには、[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)へのアクセス許可が必要です。 既定により、テナント管理者 (グローバル管理者) はこの場所にアクセスでき、コンプライアンス責任者やその他のユーザーにテナント管理者のすべての権限を与えることなくアクセスできます。この制限された管理に権限を付与するには、ユーザーを [**コンプライアンス管理者**] の管理者役割グループに追加することをお勧めします。 手順については、「[ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)」を参照してください。

これらのアクセス許可は、アイテム保持ポリシーと保持ラベルの作成、構成、適用にのみ必要です。 アイテム保持ポリシーと保持ラベルを構成するユーザーは、コンテンツへのアクセスを必要としません。

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルを使用する一般的なシナリオ

次の表は、アイテム保持ポリシーと保持ラベルでサポートされている保持シナリオにビジネス要件をマッピングするのに役立ちます。

|必要な作業...|ドキュメント|
|----------------|---------------|
|組織または Microsoft 365 サービスにより、保持アクションと削除アクションを効率的に設定する <br />-  Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Microsoft 365 グループ <br />- Skype for Business  <br />- Microsoft Teams <br />- Yammer ネットワーク |[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)|
|管理者とユーザーが、ドキュメントやメールに対して保持アクションと削除アクションのセットを手動で適用できるようにする <br />-  SharePoint <br />- OneDrive <br />- Outlook および Outlook on the web|[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)|
|サイト管理者が、SharePoint ライブラリ、フォルダー、ドキュメント セット内のすべてのコンテンツに既定の保持ラベルを設定できるようにする|[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)|
|ユーザーが、Outlook のルールを使用して、メールに保持ラベルを自動的に適用できるようにする|[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)|
|ドキュメントやメールに対して保持アクションと削除アクションのセットを自動的に適用する |[保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md)|
|次のようなイベントが発生したときに保持期間を開始する  <br />- 従業員が退職する <br />- 契約満了 <br />- 製品の有効期間の終了| [イベントの発生時に保持を開始する](event-driven-retention.md)|
|SharePoint で各種ドキュメントのライフサイクルを管理する| [保持ラベルを使用して、SharePoint に保存されているドキュメントのライフサイクルを管理する](auto-apply-retention-labels-scenario.md)|
|SEC Rule 17a-4 に準拠する|[Exchange Online およびセキュリティ/コンプライアンス センターを使用して SEC Rule 17a-4 に準拠する](use-exchange-online-to-comply-with-sec-rule-17a-4.md) |
|保持期間の終了時にコンテンツが削除される前に、誰かがレビューと承認を行うようにする|[廃棄確認](disposition.md#disposition-reviews) |
| 保持ラベルが適用される方法と場所を監視する | [保持ラベルの監視](retention.md#monitoring-retention-labels) |
|ドキュメントとメールに対して 1 つのレコード管理ソリューションを使用する |[レコード管理の詳細](records-management.md) |

レコード管理用の保持ラベルを使用する場合、コンテンツをレコードとしてマークする保持ラベルに固有の追加のシナリオがあります。 「[レコード管理の一般的なシナリオ](get-started-with-records-management.md#common-scenarios-for-records-management)」を参照してください。

## <a name="end-user-documentation-for-retention-labels"></a>保持ラベルに関するエンド ユーザー向けのドキュメント

アイテム保持ポリシーとは異なり、保持ラベルには Microsoft 365 アプリに UI があります。 保持ラベルを運用ネットワークに展開する前に、エンド ユーザーとヘルプ デスクに必ずガイダンスを提供してください。

最も効果的なエンド ユーザー向けのドキュメントは、選択した保持ラベル名と構成に関するカスタマイズされたガイダンスと手順です。 ただし、基本的な手順については次の情報を使用できます。

- [保持ラベルを手動で適用する](create-apply-retention-labels.md#manually-apply-retention-labels)
