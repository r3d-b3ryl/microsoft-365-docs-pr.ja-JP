---
title: 脅威から保護する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 管理者は、Microsoft 365 の脅威保護について説明し、組織での使用方法を構成できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8f1cecbb3141b4751778212025e5aad582707e12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826827"
---
# <a name="protect-against-threats"></a>脅威から保護する

Microsoft 365 には、さまざまな脅威保護機能が含まれています。 チェックリストとして使用できるクイック スタート ガイドを以下に示します。組織で脅威保護機能が設定されているか確認します。 Office 365 の脅威保護機能を使用したのが新しい場合、または開始する場所が不適切な場合は、次のガイダンスを出すための開始点として使用してください。

> [!IMPORTANT]
> **初期推奨される設定はポリシーの種類ごとに適用されています。ただし、多くのオプションを利用できます。また、組織固有のニーズに合わせて設定を調整できます**。 ポリシーまたは変更がデータセンターに通過するまで、約 30 分間の制限を行います。

## <a name="requirements"></a>Requirements

### <a name="subscriptions"></a>サブスクリプション

脅威保護機能は、すべての Microsoft 365 サブスクリプションに含まれています。ただし、一部のサブスクリプションにはより高度な機能が含まれています。 次の表は、この記事に含まれている保護機能とサブスクリプションの最小要件を示しています。

****

|保護の種類|サブスクリプションの要件|
|---|---|
|マルウェア対策保護|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)|
|メールおよび Office ドキュメント内の悪意のある URL およびファイルからの保護|[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)|
|フィッシング対策保護|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|高度なフィッシング対策保護|[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|スパム対策保護|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|ゼロア自動消去 (メールの場合)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|監査ログ (これはレポート目的で使用されます)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a>ロールと権限

セキュリティ センターでポリシーを構成するには、適切な役割が割 [り当&必要があります](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。 次の表にいくつかの例があります:

****

|役割または役割グループ|詳細情報|
|---|---|
|全体管理者|[Microsoft 365 管理者ロールについて](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|セキュリティ管理者|[Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織の管理|[Exchange Online のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>および<br> [Exchange Online の PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

詳細については、セキュリティ コンプライアンス センター [の「アクセス許可」 &amp; を参照してください](permissions-in-the-security-and-compliance-center.md)。

## <a name="part-1---anti-malware-protection"></a>第 1 部 - マルウェア対策保護

[マルウェア対策保護は EOP](anti-malware-protection.md) を含むサブスクリプションで利用 [できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

1. セキュリティ/[コンプライアンス &で脅威](https://protection.office.com)管理**ポリシーのマルウェア**  >  **Policy**  >  **対策を選択します**。

2. 既定のポリシーを **ダブルクリック** し、[設定] を選択 **します**。

3. 以下の設定を指定します。

    - [マルウェア **検出応答] セクションで、** 既定の設定を [いいえ] のまま **にします**。

    - [共通の **添付ファイルの種類フィルター] セクション** で、[オン] を **クリックします**。

4. [**保存**] をクリックします。

マルウェア対策ポリシー オプションの詳細については、「マルウェア対策 [ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。

## <a name="part-2---protection-from-malicious-urls-and-files"></a>パート 2 - 悪意のある URL とファイルからの保護

悪意のある URL やファイルからのクリック時保護は [、Office 365 ATP (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) を含むサブスクリプションで利用できます [。ATP](atp-safe-attachments.md) の安全な添付ファイルや [ATP](atp-safe-links.md) の安全なリンクのポリシーによってセットアップされます。

### <a name="atp-safe-attachments-policies"></a>ATP の安全な添付ファイル機能のポリシー

[ATP の安全な添付ファイル機能を設定するには](atp-safe-attachments.md)、少なくとも 1 つの ATP の安全な添付ファイルに対するポリシーを定義する必要があります。

1. セキュリティ/[コンプライアンス センター&で、脅](https://protection.office.com)威管理**ポリシー**  >  **Policy**  >  **ATP の安全な添付ファイルを選択します**。

2. **SharePoint、OneDrive、Microsoft Teams の ATP を有効にするオプションを選択します**。

3. [メールの **添付ファイルの保護] セクションで** 、プラス記号 ( ) をクリックします **+** 。

4. 以下の設定を指定します。

   - [名前 **] ボックス** に、次のように入力します `Block malware` 。

   - 応答セクションで、ブロックを選択 **します**。

   - [リダイレクト **の添付ファイル]** セクションで 、[ **リダイレクトを有効にする] オプションを選択**し、検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターのメール アドレスを指定します。

   - In the **Applied to** section, choose The recipient **domain is**. 次に、ドメインを選び、[追加 **]、** または **[OK] をクリックします**。

5. [**保存**] をクリックします。

6. (**推奨される追加手順**)全体管理者または SharePoint Online 管理者は、Microsoft 365 環境に対して**DisallowInfectedFileDownload パラメーター**を*true*に設定して**[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを実行します。 (これにより、悪意があるとして検出されたファイルを開いたり、移動したり、コピーしたり、共有したりするのを防止できます。)

詳細については [、「Office 365 ATP の安全な添付ファイル ポリシーを設定](set-up-atp-safe-attachments-policies.md) し [、SharePoint、OneDrive、Microsoft Teams Office 365 ATP を有効にする」を参照してください](turn-on-atp-for-spo-odb-and-teams.md)。

### <a name="atp-safe-links-policies"></a>ATP の安全なリンク機能のポリシー

[ATP の安全なリンクを設定するには、既定](atp-safe-links.md)のポリシーを確認および編集し、特定のユーザーに対するポリシーを追加します。

1. コンプライアンス センター[から&で、脅](https://protection.office.com)威**管理ポリシー**  >  **Policy**  >  **ATP の安全なリンクを選択します**。

2. [既定] ポリシーを **ダブルクリック** します。

3. 「 **安全なリンクを使用する」セクション** で **、「Microsoft 365 Apps for enterprise、iOS および Android 用 Office」のオプション、および [保存**] をクリック **します**。

4. 特定の **受信者に適用するポリシー セクションで** 、プラス記号 ( ) をクリックします **+** 。

5. 以下の設定を指定します。

   - [名前 **] ボックス** に名前を入力 `Safe Links` します。例:

   - [処理の **選択] セクションで** 、[オン] を **クリックします**。

   - 次のオプションを選びます。

     - **安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする**

     - **組織内で送信される電子メール メッセージに安全なリンクを適用する**

     - **ユーザーが元の URL への安全なリンクをクリックしてクリックできない**

   - In the **Applied to** section, choose The recipient **domain is**. 次に、ドメインを選び、[追加 **]、** または **[OK] をクリックします**。

6. [**保存**] をクリックします。

詳細については、「[Office 365 ATP の安全なリンク ポリシーを設定する](set-up-atp-safe-links-policies.md)」をご覧ください。

## <a name="part-3---anti-phishing-protection"></a>第 3 部 - フィッシング対策保護

[フィッシング対策]

[フィッシング対策は、EOP](anti-phishing-protection.md) を含むサブスクリプションで使用 [できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。 ATP で高度なフィッシング対策 [保護を利用できます](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

次の手順では、ATP フィッシング対策ポリシーを構成する方法について説明します。 ステップは、フィッシング対策ポリシー (ATP なし) を構成するための手順と似ています。

1. セキュリティ コンプライアンス[センターで&で、](https://protection.office.com)脅**威管理**  >  **ポリシー**  >  **ATP フィッシング対策を選択します**。

2. [既定 **のポリシー] をクリックします**。

3. [偽装 **] セクションで、[** 編集] を **クリック**し、次の設定を指定します。

   - [保護する **ユーザーを追加します]** タブで、保護を有効にします。 次に、組織のボード メンバー、CEO、CFO、その他のシニア リーダーなどのユーザーを追加します。 個々のメール アドレスを入力するか、クリックして一覧を表示できます)。

   - [ドメインの**追加] タブで、** 自動的に自分**が所有するドメインを含める。** カスタム ドメインがある場合は、それらも追加します。

   - [アクション **] タブ**で、偽**装されたユーザーと**偽装されたドメイン**オプションの両方の****メッセージを検疫するを選択**します。 さらに、偽装の安全性のヒントを有効にしてください。

   - [メールボックス **インテリジェンス] タブ** で、メールボックス インテリジェンスが有効になっていることを確認します。 さらに、メールボックス インテリジェンス ベース偽装保護を有効にします。 偽装 **されたユーザーの一覧で、[電子メールが送信される] で [** 検疫] を **選択します**。

   - [ **信頼できる送信者とドメインの追加]** タブで、追加する信頼できる送信者またはドメインを指定します。

   - 設定を **確認した後、[** 設定の確認] タブで [保存] を **クリックします**。

4. **[Spoof] セクションで** **、[Edit]** をクリックし、次の設定を指定します。

   - [ス **プーフィング フィルター設定]** タブで、スプーフィング対策保護がオンになっていることを確認します。

   - [操作] タブ **で** 、[メッセージの検 **疫] を選択します**。

   - 設定を **確認した後、[** 設定の確認] タブで [保存] を **クリックします**。 (変更を加えなかった場合は、[キャンセル] を **クリックします**)。

5. 既定のポリシー設定ページを閉じます。

フィッシング対策ポリシー オプションの詳細については [、「ATP フィッシング対策ポリシーを構成する」を参照してください](configure-atp-anti-phishing-policies.md)。

## <a name="part-4---anti-spam-protection"></a>第 4 部 - スパム対策保護

[EOP を含む](anti-spam-protection.md) サブスクリプションでは、スパム対策保護を利用 [できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

1. コンプライアンス コンプライアンス[センター&脅威管理](https://protection.office.com)**ポリシーの**  >  **Policy**  >  **スパム対策を選択します**。

2. [カスタム] **タブで** 、[カスタム設定 **] を有効** にします。

3. [ **既定のスパム フィルター ポリシーを展開し**、 **ポリシーの編集]** をクリックして、次の設定を指定します。

   - [スパムおよび **バルクアクション] セクション** でしきい値を 5 または 6 に設定します。

   - 許可リスト **セクションで** 、許可されている送信者とドメインを確認 (および必要に応じて編集) します。

4. [**保存**] をクリックします。

スパム対策ポリシーのオプションの詳細については、「EOP でスパム対策 [ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。

## <a name="part-5---additional-settings-to-configure"></a>パート 5 - 構成する追加設定

マルウェア、悪意のある URL とファイル、フィッシング、スパムからの保護の構成に加えて、ゼロアリングおよび監査ログの設定を構成することをお勧めします。

### <a name="zero-hour-auto-purge-for-email"></a>ゼロアルフパージのメールの消去

[ゼロアチ](zero-hour-auto-purge.md) (ZAP) は EOP を含むサブスクリプションで利用 [できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。 この保護は既定で有効になっています。ただし、保護が有効にするには、次の条件が満たされる必要があります。

- スパム対策ポリシーの [迷惑**メール] フォルダーにメッセージを移動**[するアクションが設定されています](anti-spam-protection.md)。

- ユーザーは既定の迷惑メール設定 [を保持してお](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)り、迷惑メールの保護を無効にしていません。

詳細については、「ゼロ [アア自動消去 - スパムやマルウェアからの保護」を参照してください](zero-hour-auto-purge.md)。

### <a name="audit-logging-for-reporting-and-investigation"></a>レポートと調査の監査ログ

監査ログは Exchange Online を含むサブスクリプションで [使用できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)。 セキュリティ ダッシュボード、電子メールのセキュリティ レポート、およびエクスプローラーなどの脅[email security reports](view-email-security-reports.md)[威保護](security-dashboard.md)レポートでデータを表示[するには](threat-explorer.md)、組織の監査ログを有効にする必要があります。 詳細については、「監査ログ検索 [を有効または無効にする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="post-setup-tasks"></a>セットアップ後の作業

脅威保護機能を構成したら、それらの機能がどのように動作しているかを監視し、必要に応じてポリシーを確認して変更し、新機能とサービス更新がないかを確認します。

****

|操作|追加情報|
|---|---|
|レポートを表示して、組織に対して脅威保護機能がどのように機能しているかを確認する|[セキュリティ ダッシュボード](security-dashboard.md)<br/>[電子メール セキュリティ レポート](view-email-security-reports.md)<br/>[365 ATP Officeレポート](view-reports-for-atp.md)<br/>[脅威エクスプローラー](threat-explorer.md)|
|必要に応じて脅威保護ポリシーを定期的に確認して変更する|[セキュリティ スコア](../mtp/microsoft-secure-score.md)<br/>[スマート レポートと分析情報](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 脅威の調査および対応の機能](keep-users-safe-with-office-365-ti.md)|
|新機能およびサービス更新プログラムを確認する|[標準および対象指定リリース オプション](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Message Center](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
