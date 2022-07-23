---
title: データ ライフサイクル管理の使用を開始する
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
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: 管理者、ライセンス要件、および組織のデータのライフサイクルを管理する一般的なシナリオの規範的な手順。
ms.openlocfilehash: f07d83a26f874fe9f4572ab0656b542beb9b8a91
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66942386"
---
# <a name="get-started-with-data-lifecycle-management"></a>データ ライフサイクル管理の使用を開始する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

保持する必要のあるコンテンツを保持し、その必要のないコンテンツを削除することにより、組織のデータのライフサイクルの管理を開始する用意はできていますか? 作業を開始するには、Microsoft Purview データ ライフサイクル管理 (以前の Microsoft Information Governance) に関する次のガイダンスを使用します。

1. Microsoft 365 で **保持と削除がどのように機能するか** を理解し、アイテム保持ポリシーが必要なワークロードを特定し、例外の保持ラベルを作成する必要があるかどうかを確認する: [保持についての説明](retention.md)
    
    > [!NOTE]
    > ビジネス、法律、または規制の記録管理要件のために価値の高いアイテムの管理が必要な場合: データ ライフサイクル管理ではなく、[レコード管理](records-management.md)で保持ラベルを使用します。

2. 組織のポリシーまたは業界の規制に必要な保持設定とアクションを指定して、特定したワークロードの **アイテム保持ポリシーを作成する**: [アイテム保持ポリシーを作成する](create-retention-policies.md)
    
    必要に応じて、[例外の保持ラベルを作成して適用します](create-retention-labels-information-governance.md)。

3. **メールボックスのアーカイブを有効にして**、ユーザーに追加のメールボックス ストレージ スペースを提供する: [Microsoft Purview コンプライアンス ポータルでアーカイブ メールボックスを有効します](enable-archive-mailboxes.md)
    
    アーカイブ メールボックスをサポートする必要がある場合は、以下のようにします:
    
    - 100 GB を超えるストレージを必要とするメールボックスの[自動拡張アーカイブを有効にします](enable-autoexpanding-archiving.md)。
    
    - メールがユーザーのプライマリ メールボックスからアーカイブ メールボックスに自動的に移動される方法をカスタマイズする必要がある場合、またはメールボックス全体ではなく、特定のフォルダーの保持と削除の設定を指定する必要がある場合は、[メッセージング レコード管理 (MRM) のアイテム保持ポリシーで保持タグを使用](set-up-an-archive-and-deletion-policy-for-mailboxes.md)します。

4. 従業員が組織を離れた後もメールボックスの内容を保持する **非アクティブなメールボックスを理解して管理する**: [非アクティブなメールボックスについての説明](inactive-mailboxes-in-office-365.md)

5. 管理するデータを含む PST ファイルがある場合: ネットワーク アップロードまたはドライブ配布を使用して **PST ファイルをオンライン メールボックスにインポートする**: [組織の PST ファイルのインポートについての説明](importing-pst-files-to-office-365.md)

## <a name="subscription-and-licensing-requirements"></a>サブスクリプションサブスクリプションとライセンスの要件

さまざまなサブスクリプションがデータ ライフサイクル管理機能をサポートしています。

Microsoft Purview 機能のメリットを得られるようにユーザーにライセンスを付与するためのオプションを確認するには、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。 このページにリストされている機能については、「[Microsoft Purview データ ライフサイクル管理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-data-lifecycle-management)」セクションおよび機能レベルのライセンス要件についての関連する [PDF ダウンロード](https://go.microsoft.com/fwlink/?linkid=2139145)を参照してください。

## <a name="permissions"></a>アクセス許可

Microsoft 365 の保持を管理するための役割と役割グループについては、次のセクションを参照してください。

アーカイブ、非アクティブなメールボックス、およびインポート用のメールボックスを管理するためのアクセス許可には、通常、メール受信者の役割などの Exchange アクセス許可が必要です。 既定では、この役割は受信者管理および組織管理役割グループに割り当てられています。 各管理タスクの正確な権限要件については、管理手順に付属のドキュメントを参照してください。

### <a name="permissions-for-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルのアクセス許可

アイテム保持ポリシーと保持ラベルを作成して管理するコンプライアンス チームのメンバーには、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>へのアクセス許可が必要です。既定により、テナント管理者 (グローバル管理者) はこの場所にアクセスでき、コンプライアンス責任者やその他のユーザーにテナント管理者のすべての権限を与えることなくアクセスできます。この制限された管理に権限を付与するには、ユーザーを **コンプライアンス管理者** の管理者役割グループに追加することをお勧めします。

この既定の役割を使用する代わりに、新しい役割グループを作成し、**保持管理** の役割をこのグループに追加することもできます。読み取り専用の役割の場合は、**閲覧限定保持管理** を使用します。 

ユーザーを既定の役割に追加する手順、または独自の役割グループを作成する手順については、「[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md)」を参照してください。

これらのアクセス許可は、アイテム保持ポリシーと保持ラベルの作成、構成、適用にのみ必要です。 これらのポリシーとラベルを構成するユーザーは、コンテンツへのアクセスを必要としません。

## <a name="common-scenarios"></a>一般的なシナリオ

次の表を使用して、ビジネス要件をデータ ライフサイクル管理の最も一般的なシナリオにマッピングします。

|必要な作業...|ドキュメント|
|----------------|---------------|
|Microsoft 365 サービスのデータを効率的に保持または削除します。 <br />-  Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Microsoft 365 グループ <br />- Teams <br />- Yammer <br />- Skype for Business |[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)|
|ユーザーに追加のメールボックス ストレージを提供する |[Microsoft Purview コンプライアンス ポータルでアーカイブ メールボックスを有効にする](enable-archive-mailboxes.md)|
|従業員が組織を離れた後にメールボックスのデータを保持する |[非アクティブなメールボックスを作成および管理する](create-and-manage-inactive-mailboxes.md)|
|PST ファイルからメールボックス データをアップロードする |[ネットワーク アップロードを使用して PST ファイルをインポートする](use-network-upload-to-import-pst-files.md)|


個々のアイテムのデータ管理が必要なシナリオがある場合は、[レコード管理の一般的なシナリオ](get-started-with-records-management.md#common-scenarios)を参照してください。 

## <a name="end-user-documentation"></a>エンド ユーザー向けのドキュメント

Microsoft 365 の保持をサポートするエンドユーザー向けドキュメントについては、次のセクションを参照してください。

非アクティブなメール ボックスのデータ ライフサイクル管理機能と PST ファイルのインポートは、管理者のみが実行できる操作であるため、エンド ユーザー向けのドキュメントは必要ありません。 この機能を有効にした後、ユーザーが Outlook でアーカイブ メールボックスの仕組みを理解し操作できるようにするには、「[オンライン アーカイブ メールボックスを使用して電子メール ストレージを管理する](https://support.microsoft.com/office/manage-email-storage-with-online-archive-mailboxes-1cae7d17-7813-4fe8-8ca2-9a5494e9a721)」を参照してください。

### <a name="end-user-documentation-for-retention-and-deletion"></a>保持と削除に関するエンドユーザー向けドキュメント

ほとんどのアイテム保持ポリシーは、ユーザーの操作なしでバック グラウンドで目立たないように機能するため、ユーザー向けのドキュメントをほとんど必要としません。 Teams のアイテム保持ポリシーは、メッセージが削除されたときに、[アイテム保持ポリシーに関する Teams メッセージ](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)へのリンクとともにユーザーに通知します。

ただし、保持ポリシーを保持ラベルで補足した場合、これらのラベルは Microsoft 365 アプリで UI に存在します。 これらのラベルを実稼働ネットワークに展開する前に、エンドユーザーとヘルプ デスクに情報と手順を提供するようにしてください。 ユーザーが SharePoint および OneDrive で保持ラベルを適用できるようにするには、「[SharePoint または OneDrive のファイルに保持ラベルを適用する](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df)」を参照してください。

最も効果的なエンドユーザー向けドキュメントは、常に、選択した保持ラベルの名前と構成に対して提供するカスタマイズされたガイダンスと指示になります。 次のページを表示して、ユーザーのトレーニングに使用できるアイテムをダウンロードします。[アイテム保持ラベルのエンド ユーザー トレーニング](https://microsoft.github.io/ComplianceCxE/enduser/retention/)。

