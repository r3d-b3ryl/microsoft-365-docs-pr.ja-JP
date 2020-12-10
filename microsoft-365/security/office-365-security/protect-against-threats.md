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
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 管理者は、Microsoft 365 の脅威保護について学習し、組織での使用方法を構成することができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 646fff4550de2e07342c0fef04952846db65a8eb
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615122"
---
# <a name="protect-against-threats"></a>脅威から保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Office 365 の Defender の構成をチャンクに分割するクイックスタートガイドを次に示します。 Office 365 の脅威保護機能に慣れておらず、どこから始めるかがわからない場合や、 *実行* するのが最適な場合は、このガイドをチェックリストと開始点として使用します。

> [!IMPORTANT]
> **ポリシーの種類ごとに最初に推奨される設定が含まれています。ただし、多くのオプションを使用できます。また、特定の組織のニーズに合わせて設定を調整することもでき** ます。 使用しているポリシーまたは変更がデータセンターによって処理されるまで約30分間待機します。

## <a name="requirements"></a>要件

### <a name="subscriptions"></a>サブスクリプション

脅威保護機能は、Microsoft または Office 365 の *すべて* のサブスクリプションに含まれています。ただし、一部のサブスクリプションには、高度な機能があります。 以下の表に、この記事に含まれる保護機能と最小のサブスクリプション要件を示します。

> [!TIP]
> 監査を有効にする *方法* 以外に、「Office 365 Exchange Online Protection (**EOP**) の一部としてマークされているマルウェア対策、フィッシング対策、およびスパム対策を開始することに注意してください。 この点は、「お忘れなく (**office 365**)」に記載されている、EOP を使用していることを覚えていない限り、office 365 の defender では奇妙に見えることがあります。

****

|保護の種類|サブスクリプションの要件|
|---|---|
|監査ログ (レポート用)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|マルウェア対策保護|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|フィッシング対策保護|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|スパム対策保護|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|ゼロ時間自動削除 (電子メール用)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|電子メールおよび Office ドキュメント内の悪意のある Url やファイルからの保護 (安全なリンクと安全な添付ファイル)|[Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|SharePoint、OneDrive、Microsoft Teams のワークロードに対して ATP を有効にする|[Office 365 の Defender ](atp-for-spo-odb-and-teams.md)|
|高度なフィッシング対策保護|[Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>ロールと権限

Office 365 ポリシーの Defender を構成するには、 [セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)で適切な役割が割り当てられている必要があります。 これらの操作を実行できる役割については、以下の表を参照してください。

****

|役割または役割グループ|詳細情報|
|---|---|
|グローバル管理者|[Microsoft 365 管理者ロールについて](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|セキュリティ管理者|[Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織の管理|[Exchange Online のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> および <p> [Exchange Online の PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

詳細については、「 [セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>開始する前に、レポートと調査の監査ログを有効にします。

事前に監査ログを開始します。 次の手順の **一部については、** 監査が必要になります。 監査ログは、 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)を含むサブスクリプションで利用できます。 [セキュリティダッシュボード](security-dashboard.md)、[電子メールセキュリティレポート](view-email-security-reports.md)、[エクスプローラー](threat-explorer.md)などの脅威保護レポートのデータを表示するためには、監査ログを *オンに* する必要があります。 詳細については、「 [監査ログの検索を有効または無効](../../compliance/turn-audit-log-search-on-or-off.md)にする」を参照してください。

## <a name="part-1---anti-malware-protection"></a>パート 1-マルウェア対策保護

[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションでは[、マルウェア対策保護](anti-malware-protection.md)を利用できます。

1. [ [セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[ **脅威管理** \> **ポリシー** の \> **マルウェア対策**] を選択します。

2. [ **既定** のポリシー] をダブルクリックし、[ **設定**] を選択します。

3. 次の設定を指定します。

    - [ **マルウェア検出の応答** ] セクションで、既定の設定の [ **いいえ**] をそのまま使用します。

    - [ **一般的な添付ファイルの種類のフィルター** ] セクションで、 **[オン**] を選択します。

4. **[保存]** をクリックします。

マルウェア対策ポリシーオプションの詳細については、「 [マルウェア対策ポリシーを構成](configure-anti-malware-policies.md)する」を参照してください。

## <a name="part-2---anti-phishing-protection"></a>パート 2-フィッシング対策保護

[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションでは、[フィッシング対策保護](anti-phishing-protection.md)を利用できます。 Advanced フィッシング対策の詳細については、「 [Defender For Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。

次の手順では、Office 365 の Microsoft Defender でフィッシング対策ポリシーを構成する方法について説明します。 手順は、EOP でフィッシング対策ポリシーを構成する場合と似ています。

1. [ [セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] を選択します。

2. [ **既定のポリシー**] をクリックします。

3. [ **偽装** ] セクションで、[ **編集**] をクリックし、次の設定を指定します。

   - [ **保護するユーザーの追加** ] タブで、 *[* 保護] をオンにします。 次に、組織の取締役会のメンバー、CEO、CFO、その他のシニアリーダーなどのユーザーを追加します。 (個々の電子メールアドレスを入力するか、クリックしてリストを表示することができます。)

   - [ **保護するドメインの追加** ] タブで、 **自分が所有しているドメインを自動的** に有効にします。 カスタムドメインがある場合は、ここで追加します。

   - [**操作**] タブで、[**偽装** されたユーザーと **偽装ドメイン** の両方の **メッセージを検疫** する] を選択します。 また、偽装の安全のヒントを有効にします。

   - [ **メールボックスインテリジェンス** ] タブで、メールボックスインテリジェンスが有効になっていることを確認し、メールボックスインテリジェンスに基づく偽装保護をオンにします。 [偽装され **たユーザーがメールを送信した場合** ] で、[ **メッセージを検疫** する] を選択します。

   - [ **信頼できる差出人とドメインの追加** ] タブで、追加する信頼できる送信者またはドメインを指定します。

   - 設定を確認した後、[**設定の確認**] タブに **保存** します。

4. [ **スプーフィング** ] セクションで、[ **編集**] をクリックし、次の設定を指定します。

   - [ **スプーフィングフィルターの設定** ] タブで、[スプーフィング対策] 保護が有効になっていることを確認します。

   - [ **Actions** ] タブで、[ **メッセージを検疫する**] を選択します。

   - 変更内容を確認した後、[**設定の確認**] タブに **保存** します。 (変更を行っていない場合は、 **キャンセル** します)。

5. [既定のポリシー設定] ページを閉じます。

フィッシング対策ポリシーオプションの詳細については、「 [Configure フィッシング対策ポリシーを Microsoft Defender の Office 365 に構成](configure-atp-anti-phishing-policies.md)する」を参照してください。

## <a name="part-3---anti-spam-protection"></a>パート 3-スパム対策保護

[スパム対策保護](anti-spam-protection.md) は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションで使用できます。

1. [[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理** ポリシーのスパム対策] を選択し \>  \> ます。

2. [ **カスタム** ] タブで、[ユーザー設定] をオンにします。

3. [ **既定のスパムフィルターポリシー**] を展開し、[ **ポリシーの編集**] をクリックして、次の設定を指定します。

   - [ **スパムと一括操作** ] セクションで、しきい値を5または6に設定します。

   - [ **許可するリスト** ] セクションで、許可された送信者とドメインを確認 (または編集) します。

4. **[保存]** をクリックします。

スパム対策ポリシーオプションの詳細については、「 [CONFIGURE EOP」の「スパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>パート 4-悪意のある Url およびファイル (「安全なリンク」と「安全な添付ファイル」 (Office 365 の場合は Defender) からの保護)

悪意のある Url やファイルからのクリック時の保護は、 [Microsoft Defender For Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)を含むサブスクリプションで利用できます。 これは、安全な [添付ファイル](atp-safe-attachments.md) と [安全なリンク](atp-safe-links.md) のポリシーによって設定されます。

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の安全な添付ファイルポリシー

[安全な添付ファイル](atp-safe-attachments.md)を設定するには、少なくとも1つの安全なリンクポリシーを作成します。

1. [ [セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] を選択し、[ **作成**] をクリックします。

2. 表示される **新しい安全な添付ファイルポリシー** ウィザードで、次の設定を構成します。

   - [ **名前** ] ボックスに「 `Block malware` 」と入力し、[ **次へ**] をクリックします。

   - [ **設定** ] ページで、次の設定を構成します。
     - [ **安全な添付ファイルの不明なマルウェアの応答** ] セクションで、[ **ブロック**] を選択します。
     - [ **添付ファイルのリダイレクト** ] セクションで、[ **リダイレクトを有効にする**] オプションを選択します。 組織のセキュリティ管理者またはオペレーターの電子メールアドレスを指定して、検出されたファイルを確認します。

     **[次へ]** をクリックします。

3. [ **適用先** ] ページで、[ **条件の追加**] をクリックし、[次の場合は適用] を選択し **ます。受信者のドメインが** である場合は、[ **追加**] をクリックし、ドメインまたはドメインを選択し、[ **追加**] **をクリックし**、[ **次へ**] をクリックします。

4. 設定内容を確認し、[ **完了**] をクリックします。

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の「安全なリンク」ポリシー

[安全なリンク](atp-safe-links.md)を設定するには、安全なリンクのためのグローバル設定を確認して編集し、少なくとも1つの安全なリンクポリシーを作成します。

1. [ [セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] を選択し、[ **グローバル設定**] をクリックして、次の設定を構成します。

   - **「安全なリンクの使用」** を確認してください。 Office 365 アプリケーションはオンになっています。オン ![ に ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) します。
   - **ユーザーが [安全なリンク] をクリックしたときに追跡しない**: この設定をオフにして、ユーザーのクリックを追跡します: ![ トグルオフ ](../../media/scc-toggle-off.png) 。
   - **ユーザーが安全なリンクをクリックして元の URL に移動できないようにする**: この設定がオンになっていることを確認します。オン ![ にし ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ます。

   完了したら、**[保存]** をクリックします。

2. [信頼できるメインリンク] ページに戻り、[ **作成**] をクリックします。

3. [ **安全なリンクの作成] ポリシー** ウィザードが表示されたら、次の設定を構成します。

   - [ **名前** ] ボックスに、などの名前を入力し、 `Safe Links` [ **次へ**] をクリックします。

   - [ **設定** ] ページで、次の設定を構成します。
     - [**メッセージ内の不明な悪意のある url に対するアクション** **: 選択]** を選択します。
     - **Microsoft Teams 内の不明または悪意のある url に対するアクションを選択** します。 **[選択] を選択し** ます。
     - **組織内で送信される電子メールメッセージに安全なリンクを適用する**
     - **メッセージを配信する前に URL スキャンが完了するまで待機する**
     - **組織内で送信される電子メールメッセージに安全なリンクを適用する**
     - **ユーザーが元の URL にクリックできないようにする**

     [ **次へ**] をクリックします。

4. [ **適用先** ] ページで、[ **条件の追加**] をクリックし、[次の場合は適用] を選択し **ます。受信者のドメインが** である場合は、[ **追加**] をクリックし、ドメインまたはドメインを選択し、[ **追加**] **をクリックし**、[ **次へ**] をクリックします。

5. 設定内容を確認し、[ **完了**] をクリックします。

詳細については、「[安全なリンク ポリシーを設定する](set-up-atp-safe-links-policies.md)」をご覧ください。

## <a name="part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>パート 5-SharePoint、OneDrive、Microsoft Teams の ATP が有効になっていることを確認する

SharePoint、OneDrive、Teams などのワークロードは、共同作業のために構築されています。 Office 365 の Defender を使用すると、チームサイトやドキュメントライブラリで悪意のあるファイルをブロックおよび検出することができます。 この機能の詳細については、 [こちら](atp-for-spo-odb-and-teams.md)を参照してください。

> [!IMPORTANT]
> **この手順を開始する前に、Microsoft 365 環境の監査ログが既に有効になっていることを確認して** ください。 これは、通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。 詳細については、「 [監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」を参照してください。

1. [ [セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] を選択し、[ **グローバル設定**] をクリックします。

2. [ **SharePoint、OneDrive、および Microsoft Teams の ATP をオン** にする] のオン/オフを確認し、[オン] をクリックして、 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) [ **保存**] をクリックします。

3. 組織の [安全な添付ファイルポリシー](set-up-atp-safe-attachments-policies.md) と [安全なリンクのポリシー](set-up-atp-safe-links-policies.md)を確認し、必要に応じて編集します。

4. 勧めグローバル管理者または SharePoint Online 管理者として、 _DisallowInfectedFileDownload_ パラメーターをに設定して **[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを実行し `$true` ます。

   - `$true` 検出されたファイルのすべてのアクション (削除を除く) をブロックします。 ユーザーは、検出されたファイルを開いたり、移動、コピー、または共有したりできません。
   - `$false` 削除とダウンロード以外のすべてのアクションをブロックします。 ユーザーは、リスクを容認し、検出されたファイルをダウンロードすることを選択できます。

   > [!TIP]
   > Microsoft 365 での PowerShell の使用の詳細については、「 [Manage microsoft 365 With powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)」を参照してください。

5. 変更がすべての Microsoft 365 データセンターに蔓延するまで最大30分かかります。

### <a name="now-set-up-alerts-for-detected-files"></a>検出されたファイルの通知を設定する

SharePoint Online、OneDrive for Business、または Microsoft Teams のファイルが悪意のあるものとして識別された場合に通知を受け取るには、警告を設定します。

1. [[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、 **[通知の** 管理] を選択し \> ます。

2. [ **新しい通知ポリシー**] を選択します。

3. 通知の名前を指定します。 たとえば、ライブラリに悪意のあるファイルを入力することができます。

4. 通知の説明を入力します。 たとえば、SharePoint Online、OneDrive、Microsoft Teams で悪意のあるファイルが検出されたときに管理者に通知を入力できます。

5. [ **この通知を送信するタイミング** ] セクションで、次のように設定します。

   a. [ **アクティビティ** ] リストで、[ **検出されたマルウェア (ファイル内**)] を選択します。

   b. [ **ユーザー** ] フィールドは空のままにします。

6. [ **この通知を送信する** ユーザー...] セクションで、悪意のあるファイルが検出されたときに通知を受信する必要がある1つ以上のグローバル管理者、セキュリティ管理者、またはセキュリティ閲覧者を選択します。

7. **保存** します。

通知の詳細については、「 [セキュリティ & コンプライアンスセンターでアクティビティ警告を作成](../../compliance/create-activity-alerts.md)する」を参照してください。

> [!NOTE]
> 構成が完了したら、次のリンクを使用してワークロード調査を開始します。
>
>- [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)
>- [セキュリティ & コンプライアンスセンターを使用して検疫されたファイルを管理する](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [SharePoint Online、OneDrive、Microsoft Teams で悪意のあるファイルが検出された場合の対処方法](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Microsoft 365 で管理者として検疫済みメッセージおよびファイルを管理する](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>パート 6-構成する追加設定

マルウェア、悪意のある Url、ファイル、フィッシング、スパムからの保護の構成に加えて、ゼロ時間の自動削除を構成することをお勧めします。

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>EOP の電子メールのゼロ時間自動削除

[ゼロ時間自動削除](zero-hour-auto-purge.md) (ZAP) は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションで利用できます。 この保護は既定で有効になっています。ただし、保護を有効にするには、次の条件を満たす必要があります。

- スパム [対策ポリシー](anti-spam-protection.md)で、 **[迷惑メール] フォルダーにメッセージを移動** するように設定されています。

- ユーザーが既定の [迷惑メール設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)を保持していて、迷惑メールの保護がオフになっていない。

詳細については、「 [スパムおよびマルウェアに対するゼロ時間自動削除対策](zero-hour-auto-purge.md)」を参照してください。

## <a name="post-setup-tasks-and-next-steps"></a>セットアップ後のタスクと次の手順

脅威保護機能を構成した後、これらの機能がどのように動作するかを必ず監視してください。 必要な操作を実行できるように、ポリシーを確認し、改訂します。 また、価値を追加できる新機能とサービス更新をご確認ください。

****

|操作|追加情報|
|---|---|
|レポートを表示して、組織の脅威保護機能がどのように機能するかを確認する|[セキュリティダッシュボード](security-dashboard.md) <p> [電子メールセキュリティレポート](view-email-security-reports.md) <p> [Microsoft Defender for Office 365 のレポート](view-reports-for-atp.md) <p> [脅威エクスプローラー](threat-explorer.md)|
|必要に応じて脅威保護ポリシーを定期的にレビューし、改訂する|[セキュリティ スコア](../mtp/microsoft-secure-score.md) <p> [スマートレポートと分析情報](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 脅威の調査と応答機能](keep-users-safe-with-office-365-ti.md)|
|新機能とサービス更新を見る|[標準および対象のリリースオプション](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365) <p> [Message Center](https://docs.microsoft.com/microsoft-365/admin/manage/message-center) <p> [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|EOP および Defender for Office 365 の推奨される標準および厳密なセキュリティ構成の詳細について説明します。|[EOP および Microsoft Defender for Office 365 のセキュリティに関する推奨設定](recommended-settings-for-eop-and-office365-atp.md)|
