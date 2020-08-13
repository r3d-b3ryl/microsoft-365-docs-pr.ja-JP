---
title: 脅威から保護する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 管理者は、Microsoft 365 の脅威保護について学習し、組織での使用方法を構成することができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8c2786ebda18b5730e1cbe93316f0d6cc319f6a9
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656633"
---
# <a name="protect-against-threats"></a>脅威から保護する

Microsoft 365 には、さまざまな脅威保護機能が含まれています。 ここでは、組織に対して脅威保護機能がセットアップされていることを確認するためのチェックリストとして使用できる、クイックスタートガイドを紹介します。 Office 365 の脅威保護機能を初めて使用する場合や、どこから始めるべきかがわからない場合は、次のガイドを出発点としてご利用ください。

> [!IMPORTANT]
> **ポリシーの種類ごとに最初に推奨される設定が含まれています。ただし、多くのオプションを使用できます。また、特定の組織のニーズに合わせて設定を調整することもでき**ます。 使用しているポリシーまたは変更がデータセンターによって処理されるまで約30分間待機します。

## <a name="requirements"></a>要件

### <a name="subscriptions"></a>サブスクリプション

脅威保護機能は、すべての Microsoft 365 サブスクリプションに含まれています。ただし、一部のサブスクリプションには、より高度な機能が含まれています。 次の表に、この記事に含まれる保護機能を最小限のサブスクリプション要件と共に示します。

****

|保護の種類|サブスクリプションの要件|
|---|---|
|マルウェア対策保護|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)|
|メールおよび Office ドキュメント内の悪意のある URL およびファイルからの保護|[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)|
|フィッシング対策保護|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|高度なフィッシング対策保護|[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|スパム対策保護|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|ゼロ時間自動削除 (電子メール用)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|監査ログ (これはレポート目的で使用されます)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a>ロールと権限

[セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)でポリシーを構成するには、適切な役割が割り当てられている必要があります。 次の表にいくつかの例があります:

****

|役割または役割グループ|詳細情報|
|---|---|
|グローバル管理者|[Microsoft 365 管理者ロールについて](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|セキュリティ管理者|[Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織の管理|[Exchange Online のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>および<br> [Exchange Online の PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

詳細については、「 [Security &amp; コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

## <a name="part-1---anti-malware-protection"></a>パート 1-マルウェア対策保護

[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションでは[、マルウェア対策保護](anti-malware-protection.md)を利用できます。

1. [[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**  >  **ポリシー**の  >  **マルウェア対策**] を選択します。

2. [**既定**のポリシー] をダブルクリックし、[**設定**] を選択します。

3. 次の設定を指定します。

    - [**マルウェア検出の応答**] セクションで、既定の設定の [**いいえ**] をそのまま使用します。

    - [**一般的な添付ファイルの種類のフィルター** ] セクションで、 **[オン**] を選択します。

4. **[保存]** をクリックします。

マルウェア対策ポリシーオプションの詳細については、「[マルウェア対策ポリシーを構成](configure-anti-malware-policies.md)する」を参照してください。

## <a name="part-2---protection-from-malicious-urls-and-files"></a>パート 2-悪意のある Url およびファイルからの保護

悪意のある Url やファイルからのクリック時の保護は、 [Office 365 atp](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (atp) を含むサブスクリプションで利用でき、Atp の[安全な添付ファイル](atp-safe-attachments.md)と[atp の安全なリンク](atp-safe-links.md)ポリシーによって設定されます。

### <a name="atp-safe-attachments-policies"></a>ATP の安全な添付ファイルポリシー

[Atp の安全な添付ファイル](atp-safe-attachments.md)を設定するには、少なくとも1つの Atp の安全な添付ファイルポリシーを定義する必要があります。

1. [[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**  >  **ポリシー**  >  **ATP 安全添付ファイル**] を選択します。

2. [ **SharePoint、OneDrive、Microsoft Teams の ATP を有効にする**] オプションを選択します。

3. [**電子メールの添付ファイルを保護**する] セクションで、プラス記号 () をクリックし **+** ます。

4. 次の設定を指定します。

   - [**名前**] ボックスに「」と入力 `Block malware` します。

   - [応答] セクションで、[**ブロック**] を選択します。

   - [**添付ファイルのリダイレクト**] セクションで、[**リダイレクトを有効にする**] オプションを選択し、検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターの電子メールアドレスを指定します。

   - [**適用先**] セクションで、[**受信者ドメイン**] を選択します。 次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。

5. **[保存]** をクリックします。

6. (**推奨の追加手順**)グローバル管理者または SharePoint Online 管理者は、 **[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを実行して、Microsoft 365 環境の**DisallowInfectedFileDownload**パラメーターを*true*に設定します。 (これにより、ユーザーが悪意を持って検出されたファイルを開く、移動、コピー、または共有できなくなります)。

詳細については、「 [office 365 の atp の安全な添付ファイルのポリシーをセットアップ](set-up-atp-safe-attachments-policies.md)する」および「 [SharePoint、OneDrive、Microsoft Teams 用の office 365 ATP を有効](turn-on-atp-for-spo-odb-and-teams.md)にする」を参照してください。

### <a name="atp-safe-links-policies"></a>ATP の安全なリンクポリシー

[ATP の安全なリンク](atp-safe-links.md)を設定するには、既定のポリシーを確認して編集し、特定のユーザーのポリシーを追加します。

1. [[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**  >  **ポリシー**  >  **ATP セーフリンク**] を選択します。

2. [**既定**のポリシー] をダブルクリックします。

3. [**安全なリンクの使用**] セクションで、[ **Microsoft 365 Apps for enterprise]、[Office for IOS**、および Android] のオプションを選択し、[**保存**] をクリックします。

4. [**特定の受信者に適用されるポリシー** ] セクションで、プラス記号 () をクリックし **+** ます。

5. 次の設定を指定します。

   - [**名前**] ボックスに、などの名前を入力し `Safe Links` ます。

   - **[アクションの選択**] セクションで、[**オン**] を選択します。

   - 次のオプションを選択します。

     - **安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする**

     - **組織内で送信される電子メールメッセージに安全なリンクを適用する**

     - **ユーザーが元の URL への安全なリンクをクリックできないようにする**

   - [**適用先**] セクションで、[**受信者ドメイン**] を選択します。 次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。

6. **[保存]** をクリックします。

詳細については、「[Office 365 ATP の安全なリンク ポリシーを設定する](set-up-atp-safe-links-policies.md)」をご覧ください。

## <a name="part-3---anti-phishing-protection"></a>パート 3-フィッシング対策保護

[フィッシング対策]

[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションでは、[フィッシング対策保護](anti-phishing-protection.md)を利用できます。 高度なフィッシング対策を[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)で利用できます。

次の手順では、ATP のフィッシング対策ポリシーを構成する方法について説明します。 この手順は、(ATP を使用しない) フィッシング対策ポリシーの構成に似ています。

1. [[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**  >  **ポリシー**  >  **ATP のフィッシング対策**] を選択します。

2. [**既定のポリシー**] をクリックします。

3. [**偽装**] セクションで、[**編集**] をクリックし、次の設定を指定します。

   - [**保護するユーザーの追加**] タブで、[保護] をオンにします。 次に、組織の取締役会のメンバー、CEO、CFO、その他のシニアリーダーなどのユーザーを追加します。 (個々の電子メールアドレスを入力するか、クリックしてリストを表示することができます。)

   - [**保護するドメインの追加**] タブで、**自分が所有しているドメインを自動的**に有効にします。 カスタムドメインがある場合は、それらも追加します。

   - [**操作**] タブで、[**偽装**されたユーザーと**偽装ドメイン**の両方の**メッセージを検疫**する] を選択します。 さらに、[偽装の安全性に関するヒント] をオンにします。

   - [**メールボックスインテリジェンス**] タブで、[メールボックスインテリジェンス] がオンになっていることを確認します。 さらに、メールボックスインテリジェンスベースの偽装保護を有効にします。 [偽装され**たユーザーがメールを送信した場合**] で、[**メッセージを検疫**する] を選択します。

   - [**信頼できる差出人とドメインの追加**] タブで、追加する信頼できる送信者またはドメインを指定します。

   - [**設定の確認**] タブで、設定を確認した後、[**保存**] をクリックします。

4. [**スプーフィング**] セクションで、[**編集**] をクリックし、次の設定を指定します。

   - [**スプーフィングフィルターの設定**] タブで、[スプーフィング対策] 保護が有効になっていることを確認します。

   - [ **Actions** ] タブで、[**メッセージを検疫する**] を選択します。

   - [**設定の確認**] タブで、設定を確認した後、[**保存**] をクリックします。 (変更を行っていない場合は、[**キャンセル**] をクリックします)。

5. [既定のポリシー設定] ページを閉じます。

フィッシング対策ポリシーのオプションの詳細については、「 [ATP のフィッシング対策ポリシーを構成](configure-atp-anti-phishing-policies.md)する」を参照してください。

## <a name="part-4---anti-spam-protection"></a>パート 4-スパム対策保護

[スパム対策保護](anti-spam-protection.md)は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションで使用できます。

1. [[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**ポリシーのスパム対策] を選択し  >  **Policy**  >  **Anti-spam**ます。

2. [**カスタム**] タブで、[**カスタム設定**] をオンにします。

3. [**既定のスパムフィルターポリシー**] を展開し、[**ポリシーの編集**] をクリックして、次の設定を指定します。

   - [**スパムと一括操作**] セクションで、しきい値を5または6に設定します。

   - [**許可するリスト**] セクションで、許可された送信者とドメインを確認し、必要に応じて編集します。

4. **[保存]** をクリックします。

スパム対策ポリシーオプションの詳細については、「 [CONFIGURE EOP」の「スパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。

## <a name="part-5---additional-settings-to-configure"></a>パート 5-構成する追加の設定

マルウェア、悪意のある Url、ファイル、フィッシング、スパムからの保護を構成するだけでなく、ゼロ時間の自動削除と監査ログの設定を構成することをお勧めします。

### <a name="zero-hour-auto-purge-for-email"></a>電子メールのゼロ時間自動削除

[ゼロ時間自動削除](zero-hour-auto-purge.md)(ZAP) は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションで利用できます。 この保護は既定で有効になっています。ただし、保護を有効にするには、次の条件を満たす必要があります。

- スパム[対策ポリシー](anti-spam-protection.md)で、 **[迷惑メール] フォルダーにメッセージを移動**するように設定されています。

- ユーザーが既定の[迷惑メール設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)を保持していて、迷惑メールの保護がオフになっていない。

詳細については、「[スパムおよびマルウェアに対するゼロ時間自動削除対策](zero-hour-auto-purge.md)」を参照してください。

### <a name="audit-logging-for-reporting-and-investigation"></a>レポートおよび調査の監査ログ

監査ログは、 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)を含むサブスクリプションで利用できます。 [セキュリティダッシュボード](security-dashboard.md)、[電子メールセキュリティレポート](view-email-security-reports.md)、[エクスプローラー](threat-explorer.md)などの脅威保護レポートのデータを表示するには、組織に対して監査ログを有効にする必要があります。 詳細については、「[監査ログの検索を有効または無効](../../compliance/turn-audit-log-search-on-or-off.md)にする」を参照してください。

## <a name="post-setup-tasks"></a>セットアップ後のタスク

脅威保護機能を構成した後は、それらの機能がどのように動作しているかを監視し、必要に応じてポリシーを確認して変更し、新しい機能とサービスの更新について確認してください。

****

|行うこと|追加情報|
|---|---|
|レポートを表示して、組織の脅威保護機能がどのように機能するかを確認する|[セキュリティダッシュボード](security-dashboard.md)<br/>[電子メールセキュリティレポート](view-email-security-reports.md)<br/>[Office 365 ATP のレポート](view-reports-for-atp.md)<br/>[脅威エクスプローラー](threat-explorer.md)|
|必要に応じて脅威保護ポリシーを定期的にレビューし、改訂する|[セキュリティ スコア](../mtp/microsoft-secure-score.md)<br/>[スマートレポートと分析情報](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 脅威の調査と応答機能](keep-users-safe-with-office-365-ti.md)|
|新機能とサービス更新を見る|[標準および対象のリリースオプション](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Message Center](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
