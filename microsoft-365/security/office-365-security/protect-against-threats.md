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
description: 管理者は、Microsoft 365 の脅威保護について学習し、組織で使用する方法を構成できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3eec37f01bb39dda9f767ad32be96bbff43a2ee0
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683249"
---
# <a name="protect-against-threats"></a>脅威から保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


ここでは、365 用の Defender の構成をチャンクに分割するクイック スタート Office示します。 Office 365 の脅威保護機能を初めから使用する場合は、どこから開始する必要があるのか分からず、最適な方法で学習する場合は、チェックリストと開始点としてこのガイダンスを使用してください。

> [!IMPORTANT]
> **初期推奨設定はポリシー** の種類ごとに含まれていますが、多くのオプションを使用できます。また、組織の特定のニーズに合わせて設定を調整することもできます。 ポリシーまたは変更がデータセンターを経由して機能するには、約 30 分かかります。

## <a name="requirements"></a>要件

### <a name="subscriptions"></a>サブスクリプション

脅威保護機能は、すべての Microsoft *または* Office 365 サブスクリプションに含まれています。ただし、一部のサブスクリプションには高度な機能があります。 次の表に、この記事に含まれる保護機能と、最小サブスクリプション要件を示します。

> [!TIP]
> 監査を有効にする指示以外にも、Office 365 Exchange Online Protection **(EOP)** の一部としてマークされているマルウェア対策、フィッシング対策、スパム対策が開始されます。  これは、Defender for Office 365 の記事では **、(Office 365** 用 Defender) に EOP が含まれているか、EOP に組み込まれているか、または上に構築されるまで、奇数に思える可能性があります。

****

|保護の種類|サブスクリプションの要件|
|---|---|
|監査ログ (レポート用)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|マルウェア対策保護|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|フィッシング対策保護|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|スパム対策保護|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|ゼロアワー自動消去 (メール用)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|電子メールやドキュメント内の悪意のある URL やファイルOffice (安全なリンクと安全な添付ファイル) からの保護|[Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|SharePoint、OneDrive、Microsoft Teams のワークロードに対して ATP を有効にする|[Defender for Office 365 ](atp-for-spo-odb-and-teams.md)|
|高度なフィッシング対策保護|[Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>ロールと権限

Office 365 ポリシー用に Defender を構成するには、セキュリティ/コンプライアンス センターで適切な [役割&必要があります](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。 これらのアクションを実行できるロールについては、次の表を参照してください。

****

|役割または役割グループ|詳細については、次の場所を参照してください。|
|---|---|
|グローバル管理者|[Microsoft 365 管理者ロールについて](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|セキュリティ管理者|[Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織の管理|[Exchange Online のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> および <p> [Exchange Online の PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

詳細については、セキュリティ/コンプライアンス [センターの「アクセス許可&参照してください](permissions-in-the-security-and-compliance-center.md)。

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>始める前に、レポートと調査の監査ログを有効にする

監査ログを早期に開始します。 次の手順の **特定の場合** は、監査を有効にする必要があります。 監査ログは、Exchange Online を含むサブスクリプション [で使用できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)。 セキュリティ ダッシュボード、メール セキュリティ レポート、エクスプローラーなどの脅威 [](security-dashboard.md)保護レポートのデータを表示するには、[](threat-explorer.md)監査ログをオンにする必要 *があります*。 [](view-email-security-reports.md) 詳細については、「監査ログ [検索を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="part-1---anti-malware-protection"></a>パート 1 - マルウェア対策保護

[マルウェア対策保護は、EOP](anti-malware-protection.md) を含むサブスクリプションで [利用できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

1. セキュリティ/ [コンプライアンス センター&、](https://protection.office.com)脅威 **管理ポリシーの** \> **マルウェア対策** \> **を選択します**。

2. 既定のポリシーを **ダブルクリックし** 、設定を選択 **します**。

3. 次の設定を指定します。

    - [マルウェア検出 **応答] セクション** で、既定の設定 [いいえ] のままに **します**。

    - [共通の **添付ファイルの種類フィルター] セクションで** 、[オン] を **選択します**。

4. **[保存]** をクリックします。

マルウェア対策ポリシー オプションの詳細については、「マルウェア対策ポリシーを構成 [する」を参照してください](configure-anti-malware-policies.md)。

## <a name="part-2---anti-phishing-protection"></a>パート 2 - フィッシング対策保護

[フィッシング対策保護は、EOP](anti-phishing-protection.md) を含むサブスクリプションで [利用できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。 高度なフィッシング対策保護は、Defender で Office [365 で利用できます](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

次の手順では、Microsoft Defender でフィッシング対策ポリシーを Office 365 に構成する方法について説明します。 手順は、EOP でフィッシング対策ポリシーを構成する場合と似ています。

1. セキュリティ/[コンプライアンス センター&、](https://protection.office.com)脅威 **管理ポリシー** ATP フィッシング対策 \>  \> **を選択します**。

2. [既定 **のポリシー] をクリックします**。

3. [偽装 **] セクションで** 、[編集] **をクリック** し、次の設定を指定します。

   - [保護する **ユーザーの追加] タブで** 、[保護を有効にする] *をオン* にします。 次に、組織の役員、CEO、CFO、その他の上級リーダーなどのユーザーを追加します。 (個々のメール アドレスを入力するか、クリックしてリストを表示できます)。

   - On the **Add domains to protect** tab, turn on Automatically include the **domains I own**. カスタム ドメインがある場合は、ここで追加します。

   - [操作 **] タブで**、偽装したユーザーと偽装されたドメイン の両方のオプションのメッセージ **を検疫するを選択** します。 また、偽装安全性のヒントも有効にしてください。

   - [メールボックス **インテリジェンス] タブ** で、メールボックス インテリジェンスが有効になっていることを確認し、メールボックス インテリジェンス ベースの偽装保護を有効にします。 In the **If email is sent by an impersonated user** list, choose Quarantine the **message**.

   - [信頼 **できる送信者とドメイン** の追加] タブで、追加する信頼できる送信者またはドメインを指定します。

   - **設定** を **確認した後、[** 設定の確認] タブに保存します。

4. [ **スプーフィング]** セクションで、[編集 **] をクリック** し、次の設定を指定します。

   - [ **スプーフィング フィルターの設定** ] タブで、スプーフィング対策保護が有効になっていることを確認します。

   - [操作 **] タブで** 、[メッセージの **検疫] を選択します**。

   - **変更** を **確認した後、[設定の** 確認] タブに保存します。 (If you didn't make any changes, **Cancel**.)

5. 既定のポリシー設定ページを閉じます。

フィッシング対策ポリシー オプションの詳細については、「Microsoft Defender for Office [365](configure-atp-anti-phishing-policies.md)でのフィッシング対策ポリシーの構成」を参照してください。

## <a name="part-3---anti-spam-protection"></a>パート 3 - スパム対策保護

[スパム対策保護は、EOP](anti-spam-protection.md) を含むサブスクリプションで [利用できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

1. セキュリティ/[コンプライアンス センター&、](https://protection.office.com)脅威 **管理ポリシーのスパム** 対策 \>  \> **を選択します**。

2. [カスタム] **タブ** で、[カスタム設定] をオンにします。

3. [既定 **のスパム フィルター ポリシー] を展開し、[****ポリシーの** 編集] をクリックして、次の設定を指定します。

   - [スパム **と一括アクション** ] セクションで、しきい値を 5 または 6 に設定します。

   - [許可 **リスト] セクション** で、許可された送信者とドメインを確認 (または編集) します。

4. **[保存]** をクリックします。

スパム対策ポリシー オプションの詳細については [、「EOP](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」を参照してください。

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>パート 4 - 悪意のある URL とファイルからの保護 (Defender の安全なリンクと安全な添付ファイル Office 365)

悪意のある URL やファイルからのクリック時の保護は、Microsoft Defender for Office [365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)を含むサブスクリプションで利用できます。 安全な添付ファイルと[安全なリンクのポリシー](atp-safe-attachments.md)[によって](atp-safe-links.md)設定されます。

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の安全な添付ファイル ポリシー

安全な添付ファイル [を設定するには](atp-safe-attachments.md)、少なくとも 1 つの安全なリンク ポリシーを作成します。

1. セキュリティ & コンプライアンス センター [で、[](https://protection.office.com)脅威 **管理** ポリシー ATP の安全な添付ファイル] を選択し、[作成] \>  \> をクリック **します**。

2. 表示される **安全な添付ファイルの新しい** ポリシー ウィザードで、次の設定を構成します。

   - [名前 **] ボックスに** 「次へ」 `Block malware` と入力し、[次へ] を **クリックします**。

   - [設定 **] ページ** で、次の設定を構成します。
     - [安全な **添付ファイル] の [不明なマルウェアの応答** ] セクションで、[ブロック] を **選択します**。
     - [添付ファイル **のリダイレクト] セクション** で、[リダイレクトを有効にする] **オプションを選択します**。 検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターの電子メール アドレスを指定します。

     **[次へ]** をクリックします。

3. On the **Applied to** page, click **a condition,** choose **Applied if: The recipient domain is,** click **Add,** select your domains, click **Add,** click **Done,** and then click **Next**.

4. 設定を確認し、[完了] を **クリックします**。

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の安全なリンク ポリシー

安全なリンク [を設定するには](atp-safe-links.md)、安全なリンクのグローバル設定を確認および編集し、少なくとも 1 つの安全なリンク ポリシーを作成します。

1. セキュリティ &[コンプライアンス](https://protection.office.com)センターで、[**脅威管理** ポリシー ATP の安全なリンク] を選択し、[グローバル設定] をクリックして、次の \>  \> 設定を構成します。 

   - Verify **Use Safe Links in: Office 365 applications** is turned on: Toggle on ![ ](../../media/scc-toggle-on.png) .
   - **Do not track when users click Safe Links**: Turn this setting off to track user clicks: Toggle off ![ ](../../media/scc-toggle-off.png) .
   - **ユーザーが元の URL への安全な** リンクをクリックさせない: この設定がオンになっていることを確認します: ![ オンに切り替え ](../../media/scc-toggle-on.png) 。

   完了したら、**[保存]** をクリックします。

2. メインの [安全なリンク] ページに戻り、[作成] を **クリックします**。

3. 表示される **安全なリンクの作成** ポリシー ウィザードで、次の設定を構成します。

   - [名前 **] ボックス** に名前を入力し、[次へ] `Safe Links` をクリック **します**。

   - [設定 **] ページ** で、次の設定を構成します。
     - **Select the action for unknown potentially malicious URLs in messages**: Choose **On**.
     - **Microsoft Teams 内の不明な URL または悪意のある** 可能性のある URL に対するアクションを選択します。[オン] を **選択します**。
     - **組織内で送信される電子メール メッセージに安全なリンクを適用する**
     - **メッセージを配信する前に URL のスキャンが完了するのを待つ**
     - **組織内で送信される電子メール メッセージに安全なリンクを適用する**
     - **ユーザーがクリックスルーして元の URL にアクセスできない**

     [ **次へ**] をクリックします。

4. On the **Applied to** page, click **a condition,** choose **Applied if: The recipient domain is,** click **Add,** select your domains, click **Add,** click **Done,** and then click **Next**.

5. 設定を確認し、[完了] を **クリックします**。

詳細については、「[安全なリンク ポリシーを設定する](set-up-atp-safe-links-policies.md)」をご覧ください。

## <a name="part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>パート 5 - SharePoint、OneDrive、Microsoft Teams の ATP がオンになっていることを確認する

SharePoint、OneDrive、Teams のようなワークロードは、コラボレーション用に構築されています。 Defender を Office 365 に使用すると、チーム サイトやドキュメント ライブラリで悪意のあるファイルとして識別されたファイルをブロックおよび検出できます。 この機能の詳細については、以下を参照 [してください](atp-for-spo-odb-and-teams.md)。

> [!IMPORTANT]
> **この手順を開始する前に、Microsoft 365** 環境で監査ログが既に有効になっていることを確認してください。 これは通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。 詳細については、「監査ログ [検索を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。

1. セキュリティ/[コンプライアンス センターで&](https://protection.office.com)管理ポリシー ATP の安全な添付ファイルを選択し、[グローバル設定] \>  \> を **クリックします**。 

2. **SharePoint、OneDrive、Microsoft Teams** の ATP を有効にするトグルが右側に表示されるのを確認します。オンに切り替え、[保存] ![ ](../../media/scc-toggle-on.png) をクリック **します**。

3. 組織の安全な添付ファイル ポリシーと安全なリンク ポリシーを [確認](set-up-atp-safe-attachments-policies.md) (および必要に応じて編集) [します](set-up-atp-safe-links-policies.md)。

4. (推奨)全体管理者または SharePoint Online 管理者として _、DisallowInfectedFileDownload_ パラメーターを設定して **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを実行します `$true` 。

   - `$true` 検出されたファイルのすべてのアクション (Delete を除く) をブロックします。 ユーザーは、検出されたファイルを開く、移動、コピー、または共有することはできません。
   - `$false` Delete および Download 以外のすべてのアクションをブロックします。 ユーザーはリスクを受け入れて、検出されたファイルをダウンロードできます。

   > [!TIP]
   > Microsoft 365 で PowerShell を使用する方法の詳細については、「PowerShell を使用して [Microsoft 365 を管理](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)する」を参照してください。

5. 変更がすべての Microsoft 365 データセンターに分散するために最大 30 分かかります。

### <a name="now-set-up-alerts-for-detected-files"></a>検出されたファイルのアラートを設定する

SharePoint Online、OneDrive for Business、または Microsoft Teams のファイルが悪意のあるファイルとして識別された場合に通知を受け取る場合は、アラートを設定できます。

1. セキュリティ/ [コンプライアンス センターで&](https://protection.office.com)アラートの **管理を** \> **選択します**。

2. [新 **しいアラート ポリシー] を選択します**。

3. 通知の名前を指定します。 たとえば、「ライブラリ」に「悪意のあるファイル」と入力します。

4. アラートの説明を入力します。 たとえば、「SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが検出された場合に管理者に通知する」と入力できます。

5. [この通知 **をいつ送信する...] セクションで** 、次の値を設定します。

   a. [アクティビティ **] ボックスの** 一覧で、[ **ファイル内の検出されたマルウェア] を選択します**。

   b. [ユーザー **] フィールドは** 空のままにします。

6. [この警告の送信場所 **...]** セクションで、悪意のあるファイルが検出された場合に通知を受け取る必要がある 1 人または複数のグローバル管理者、セキュリティ管理者、またはセキュリティ 閲覧者を選択します。

7. **Save**.

アラートの詳細については、「セキュリティ/コンプライアンス センターでのアクティビティアラート& [参照してください](../../compliance/create-activity-alerts.md)。

> [!NOTE]
> 構成が完了したら、次のリンクを使用してワークロードの調査を開始します。
>
>- [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)
>- [セキュリティ/コンプライアンス センター&使用して検疫済みファイルを管理する](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが見つかった場合の対応方法](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Microsoft 365 で管理者として検疫済みメッセージとファイルを管理する](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>パート 6 - 構成する追加設定

マルウェア、悪意のある URL とファイル、フィッシング、スパムからの保護を構成すると共に、ゼロアワー自動消去を構成することをお勧めします。

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>EOP での電子メールのゼロアワー自動消去

[ゼロアワー自動消去](zero-hour-auto-purge.md) (ZAP) は [、EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションで利用できます。 この保護は既定で有効になっています。ただし、保護を有効にするには、次の条件を満たしている必要があります。

- スパム対策アクションは、スパム **対策ポリシーで [メッセージを迷惑メール** フォルダー [に移動する] に設定されています](anti-spam-protection.md)。

- ユーザーは、既定の迷惑メール [設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)を保持し、迷惑メール保護をオフにしていない。

詳細については、「ゼロアワー自動消去 - スパムやマルウェアに対する [保護」を参照してください](zero-hour-auto-purge.md)。

## <a name="post-setup-tasks-and-next-steps"></a>セットアップ後のタスクと次の手順

脅威保護機能を構成したら、それらの機能の動作を監視してください。 必要に応じてポリシーを確認および修正します。 また、価値を高め得る新機能やサービス更新プログラムを監視します。

****

|操作|追加情報|
|---|---|
|レポートを表示して、組織の脅威保護機能がどのように機能しているのか確認する|[セキュリティ ダッシュボード](security-dashboard.md) <p> [電子メール セキュリティ レポート](view-email-security-reports.md) <p> [Microsoft Defender for Office 365 のレポート](view-reports-for-atp.md) <p> [脅威エクスプローラー](threat-explorer.md)|
|必要に応じて脅威保護ポリシーを定期的に確認および修正する|[セキュリティ スコア](../mtp/microsoft-secure-score.md) <p> [スマート レポートと分析情報](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 脅威の調査と対応の機能](keep-users-safe-with-office-365-ti.md)|
|新機能とサービス更新プログラムを監視する|[標準リリースオプションと対象指定リリース オプション](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365) <p> [Message Center](https://docs.microsoft.com/microsoft-365/admin/manage/message-center) <p> [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|EOP および Defender for Office 365 の推奨される Standard および Strict セキュリティ構成の詳細について説明します。|[EOP と Microsoft Defender の 365 セキュリティOffice推奨設定](recommended-settings-for-eop-and-office365-atp.md)|
