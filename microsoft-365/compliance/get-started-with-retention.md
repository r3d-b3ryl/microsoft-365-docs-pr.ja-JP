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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: アイテム保持ポリシーと保持ラベルを実装して組織のデータを管理しようと思っても、どこから始めればよいかかわりませんか? 開始するのに役立つ実用的なガイダンスをご覧ください。
ms.openlocfilehash: 5d1566cc5840b93a4d3a994004ea0e1d52e01bb6
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60757360"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルの使用を開始する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

保持する必要のあるコンテンツを保持し、その必要のないコンテンツを削除することにより、組織のデータの管理を開始する用意はできていますか? 開始するには、次のガイダンスを使用してください。

1. Microsoft 365 の **保持のしくみを理解** し、アイテム保持ポリシーと保持ラベルのどちらを使用するか、または組み合わせて使用するかを決定します。[保持の詳細](retention.md)に関する記事を参照してください。

2. 組織のポリシーや業界の規制で必要とされている **保持設定とアクションを特定** します。
    
    この評価の一環として、[レコード管理](records-management.md)を使用するかどうかを決定します。

3. 特定した保持設定とアクションに基づいて、**アイテム保持ポリシーと保持ラベルを作成** します。
    
    保持ラベルの場合、[ファイル計画](file-plan-manager.md)を使用して、スプレッドシートで保持ラベルを定義および調整すると便利な場合があります。次に、そのスプレッドシートをインポートしてラベルを作成します。
    
3. **保持ラベルを発行して適用** します。 アイテム保持ポリシーは "一度設定したらそのまま" の構成を想定して設計されています。一方、保持ラベルは複数のポリシーで使用できる再利用可能な文書パーツで、ユーザーのワークフローに組み込むことができます。 保持ラベルの使用方法については、[一般的なシナリオ](#common-scenarios-for-retention-policies-and-retention-labels)の一覧を参照してください。 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルのサブスクリプションおよびライセンス要件

アイテム保持ポリシーと保持ラベルはさまざまなサブスクリプションでサポートされており、ユーザーのライセンス要件は使用する機能によって異なります。

Microsoft 365 コンプライアンス機能のメリットを得られるようにユーザーにライセンスを付与するためのオプションを確認するには、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。 保持については、「[情報ガバナンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)」セクション、および機能レベルのライセンス要件に関する PDF ダウンロード ファイルを参照してください。

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルを作成して管理するために必要なアクセス許可

アイテム保持ポリシーと保持ラベルを作成して管理するコンプライアンス チームのメンバーには、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 コンプライアンス センター</a>へのアクセス許可が必要です。 既定により、テナント管理者 (グローバル管理者) はこの場所にアクセスでき、コンプライアンス責任者やその他のユーザーにテナント管理者のすべての権限を与えることなくアクセスできます。この制限された管理に権限を付与するには、ユーザーを [**コンプライアンス管理者**] の管理者役割グループに追加することをお勧めします。

この既定の役割を使用する代わりに、新しい役割グループを作成し、**保持管理** の役割をこのグループに追加することもできます。読み取り専用の役割の場合は、**閲覧限定保持管理** を使用します。 

ユーザーを既定の役割に追加する手順、または独自の役割グループを作成する手順については、「[Microsoft 365 コンプライアンス センターのアクセス許可](microsoft-365-compliance-center-permissions.md)」を参照してください。

これらのアクセス許可は、アイテム保持ポリシーと保持ラベルの作成、構成、適用にのみ必要です。 これらのポリシーとラベルを構成するユーザーは、コンテンツへのアクセスを必要としません。

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルを使用する一般的なシナリオ

次の表は、アイテム保持ポリシーと保持ラベルでサポートされている保持シナリオにビジネス要件をマッピングするのに役立ちます。

|必要な作業...|ドキュメント|
|----------------|---------------|
|以下の Microsoft 365 サービスによる保持および削除アクションを効率的に設定します。 <br />-  Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Microsoft 365 グループ <br />- Skype for Business  <br />- Microsoft Teams <br />- Yammer ネットワーク |[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)|
|管理者とユーザーが、以下でドキュメントと電子メールの保持および削除アクションを手動で適用できるようにする <br />-  SharePoint <br />- OneDrive <br />- Outlook および Outlook on the web|[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)|
|サイト管理者が、SharePoint ライブラリ、フォルダー、またはドキュメントセット内のすべてのコンテンツの既定の保持および削除アクションを設定できるようにする|[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)|
|Outlook のルールを使用して、ユーザーが電子メールの保持および削除アクションを自動的に適用できるようにする|[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)|
|管理者が保持アクションと削除アクションをドキュメント理解モデルに適用できるようにして、SharePoint ライブラリで識別されたドキュメントにこれらが自動的に適用されるようにします。|[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)|
|ドキュメントと電子メールに保持および削除アクションを自動的に適用する |[保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md)|
|次のようなイベントが発生したときに保持期間を開始する  <br />- 従業員が退職する <br />- 契約満了 <br />- 製品の有効期間の終了| [イベントの発生時に保持を開始する](event-driven-retention.md)|
|ポリシーの変更を制限して規制要件を満たす、または不正な管理者から保護する| [保管ロックを使用して、アイテム保持ポリシーと保持ラベル ポリシーへの変更を制限する](retention-preservation-lock.md)
|保持期間の終了時にコンテンツが削除される前に、誰かがレビューと承認を行うようにする|[廃棄確認](disposition.md#disposition-reviews) |
| 保持および削除設定がアイテムに適用される方法と場所を監視する | [保持ラベルの監視](retention.md#monitoring-retention-labels) |
|ドキュメントとメールに対して 1 つのレコード管理ソリューションを使用する |[レコード管理の詳細](records-management.md) |

レコード管理用の保持ラベルを使用する場合、コンテンツをレコードとしてマークする保持ラベルに固有の追加のシナリオがあります。「[レコード管理の一般的なシナリオ](get-started-with-records-management.md#common-scenarios-for-records-management)」を参照してください。

## <a name="end-user-documentation-for-retention"></a>データ保持に関するエンド ユーザー向けのドキュメント

ほとんどのアイテム保持ポリシーは、ユーザーの操作なしでバック グラウンドで目立たないように機能するため、ユーザー向けのドキュメントをほとんど必要としません。 Teams のアイテム保持ポリシーは、メッセージが削除されたときに、[アイテム保持ポリシーに関する Teams メッセージ](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)へのリンクとともにユーザーに通知します。

保持ラベルは Microsoft 365 アプリに UI が存在するため、これらのラベルを運用ネットワークに展開する前に、エンドユーザーとヘルプ デスクにガイダンスを提供するようにしてください。 ユーザーが SharePoint および OneDrive で保持ラベルを適用できるようにするには、「[SharePoint または OneDrive のファイルに保持ラベルを適用する](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df)」を参照してください。

ただし、最も効果的なエンド ユーザー向けのドキュメントは、選択した保持ラベル名と構成に関するカスタマイズされたガイダンスと手順です。 次のページを表示して、ユーザーのトレーニングに使用できるアイテムをダウンロードします。[アイテム保持ラベルのエンド ユーザー トレーニング](https://microsoft.github.io/ComplianceCxE/enduser/retention/)。