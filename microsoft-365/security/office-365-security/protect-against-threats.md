---
title: 脅威から保護する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、Microsoft 365 の脅威保護について説明し、組織で使用する方法を構成できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b55391247bf7d21c68c67e29f93bac1b7088b035
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687089"
---
# <a name="protect-against-threats"></a>脅威から保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

365 の Defender の構成をチャンクに分割するクイック スタート Office示します。 Office 365 の脅威保護機能を初めから使用する場合は、どこから始めるのか分からず、最適な方法を学ぶ場合は、チェックリストと開始点としてこのガイダンスを使用してください。

> [!IMPORTANT]
> **最初の推奨設定は** ポリシーの種類ごとに含まれていますが、多くのオプションを使用できます。また、特定の組織のニーズに合わせて設定を調整することもできます。 ポリシーまたは変更がデータセンター経由で動作するには、約 30 分かかります。

## <a name="requirements"></a>要件

### <a name="subscriptions"></a>サブスクリプション

脅威保護機能は、Microsoft *または* 365 サブスクリプションOffice含まれています。ただし、一部のサブスクリプションには高度な機能があります。 次の表に、この記事に含まれる保護機能と最小サブスクリプション要件を示します。

> [!TIP]
> 監査を有効にする指示を超えて、手順によってマルウェア対策、フィッシング対策、スパム対策が開始され、Office 365 Exchange Online Protection **(EOP)** の一部としてマークされます。 これは、Office 365 の Defender の記事では、EOP が含まれている **(Office 365** の Defender) が含まれているとビルドされるまで、奇妙に思えます。

****

|保護の種類|サブスクリプションの要件|
|---|---|
|監査ログ (レポート用)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|マルウェア対策保護|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|フィッシング対策保護|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|スパム対策保護|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|0 時間の自動削除 (電子メールの場合)|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|電子メールおよびドキュメント内の悪意のある URL とファイルOffice保護 (安全なリンクと安全な添付ファイル)|[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|SharePoint、OneDrive、Microsoft Teams ワークロードの安全な添付ファイルを有効にする|[Microsoft Defender for Office 365](turn-on-mdo-for-spo-odb-and-teams.md)|
|高度なフィッシング対策保護|[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>ロールと権限

365 ポリシー Office Defender を構成するには、セキュリティ コンプライアンス センターで適切な役割& [必要があります](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。 これらのアクションを実行できるロールについては、以下の表を参照してください。

****

|役割または役割グループ|詳細については、次の情報を参照してください。|
|---|---|
|グローバル管理者|[Microsoft 365 管理者ロールについて](../../admin/add-users/about-admin-roles.md)|
|セキュリティ管理者|[Azure Active Directory での管理者役割のアクセス許可](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織の管理|[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo) <p> および <p> [Exchange Online の PowerShell](/powershell/exchange/exchange-online-powershell)|
|

詳細については、「セキュリティ コンプライアンス センターのアクセス許可 [」&参照してください](permissions-in-the-security-and-compliance-center.md)。

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>開始する前に、[レポートと調査の監査ログ] をオンにします。

監査ログを早期に開始します。 次の手順の特定の場合は、 **監査をオン** にする必要があります。 監査ログは、Exchange Online を含むサブスクリプション [で使用できます](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)。 セキュリティ ダッシュボード、電子メール セキュリティ レポート、エクスプローラーなどの脅威保護レポート [](view-email-security-reports.md)のデータを表示するには [](threat-explorer.md)、監査ログをオンにする必要 *があります*。 [](security-dashboard.md) 詳細については、「監査ログ検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="part-1---anti-malware-protection"></a>パート 1 - マルウェア対策保護

[マルウェア対策保護は、EOP](anti-malware-protection.md) を含むサブスクリプションで [利用できます](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

1. [セキュリティ と [コンプライアンス &] で、[](https://protection.office.com)脅威 **管理** ポリシーマルウェア \> **対策** \> **] を選択します**。

2. [既定のポリシー] を **ダブルクリック** し、[設定] を **選択します**。

3. 次の設定を指定します。

    - [マルウェア **検出応答] セクション** で、既定の設定を **[いいえ**] のままにします。

    - [共通の **添付ファイルの種類フィルター] セクションで** 、[オン] を **選択します**。

4. **[保存]** をクリックします。

マルウェア対策ポリシー オプションの詳細については、「マルウェア対策ポリシーを構成 [する」を参照してください](configure-anti-malware-policies.md)。

## <a name="part-2---anti-phishing-protection"></a>パート 2 - フィッシング対策の保護

[フィッシング対策保護は、EOP](anti-phishing-protection.md) を含むサブスクリプションで [利用できます](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。 高度なフィッシング対策保護は [、Defender で 365 Officeできます](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

次の手順では、Microsoft Defender でフィッシング対策ポリシーを 365 用に構成Officeします。 EOP でフィッシング対策ポリシーを構成する手順は似ています。

1. [セキュリティ [& コンプライアンス センター](https://protection.office.com)] で、[脅威 **管理** ポリシー ATP のフィッシング対策] \>  \> **を選択します**。

2. [既定 **のポリシー] をクリックします**。

3. [偽装 **] セクションで** 、[編集] **をクリック** し、次の設定を指定します。

   - [保護する **ユーザーの追加] タブで** 、[保護を有効にする] *をオン* にします。 次に、組織の役員、CEO、CFO、その他の上級リーダーなどのユーザーを追加します。 (個々の電子メール アドレスを入力するか、クリックしてリストを表示できます)。

   - [保護する **ドメインの追加] タブ** で、[所有するドメインを自動的に含める **] をオンにします**。 カスタム ドメインがある場合は、今すぐ追加します。

   - [操作 **] タブで**、[偽装されたユーザーと偽装されたドメイン オプションの両方についてメッセージ **を検疫する] を選択** します。 また、偽装の安全に関するヒントも有効にしてください。

   - [メールボックス **インテリジェンス] タブ** で、メールボックス インテリジェンスが有効になっていることを確認し、メールボックス インテリジェンス ベースの偽装保護を有効にします。 [偽装 **されたユーザーから電子メール** が送信された場合] ボックスの一覧で、[メッセージの **検疫] を選択します**。

   - [信頼 **できる送信者とドメインの** 追加] タブで、追加する信頼できる送信者またはドメインを指定します。

   - **設定** を **確認した後、[** 設定の確認] タブに保存します。

4. [スプー **フィング]** セクションで、[編集] **をクリック** し、次の設定を指定します。

   - [ス **プーフィング フィルターの設定** ] タブで、スプーフィング対策保護が有効になっていることを確認します。

   - [操作] **タブで** 、[メッセージの **検疫] を選択します**。

   - **変更** を確認 **した後、[設定の** 確認] タブに保存します。 (変更を加えなかった場合は、 **キャンセル** します。)

5. 既定のポリシー設定ページを閉じます。

フィッシング対策ポリシー オプションの詳細については、「Configure anti-フィッシング ポリシー in [Microsoft Defender for microsoft Defender for Office 365」を参照してください](configure-atp-anti-phishing-policies.md)。

## <a name="part-3---anti-spam-protection"></a>パート 3 - スパム対策保護

[スパム対策保護は、EOP](anti-spam-protection.md) を含むサブスクリプション [で利用できます](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

1. セキュリティ 管理 [コンプライアンス センター&で、[](https://protection.office.com)脅威 **管理** ポリシースパム \> **対策** \> **] を選択します**。

2. **[カスタム]** タブで、[カスタム] 設定をオンにします。

3. [既定 **のスパム フィルター ポリシー] を展開** し、[ポリシー **の編集**] をクリックし、次の設定を指定します。

   - **[迷惑メールおよびバルク メールの処理**] セクションで、しきい値を 5 または 6 に設定します。

   - [許可 **リスト] セクション** で、許可されている送信者とドメインを確認 (および/または編集) します。

4. **[保存]** をクリックします。

スパム対策ポリシー オプションの詳細については、「EOP でスパム対策ポリシーを構成する」 [を参照してください](configure-your-spam-filter-policies.md)。

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>パート 4 - 悪意のある URL とファイルからの保護 (Defender の安全なリンクと安全な添付Office 365)

悪意のある URL やファイルからのクリック時の保護は、Microsoft Defender for Office [365 を含むサブスクリプションで利用できます](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。 これは、安全な添付ファイル[と安全なリンク](safe-attachments.md)[ポリシーを通じて](safe-links.md)設定されます。

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender の安全な添付ファイル ポリシー (Office 365)

安全な添付ファイル [を設定するには](safe-attachments.md)、少なくとも 1 つの安全なリンク ポリシーを作成します。

1. セキュリティ コンプライアンス [センターで、[脅威&](https://protection.office.com)ポリシー  ATP の安全な添付ファイル] を選択し、[ \>  \> 作成] を **クリックします**。

2. 表示される **[新しい安全な添付ファイル]** ポリシー ウィザードで、次の設定を構成します。

   - [名前] **ボックスに** 「」と `Block malware` 入力し、[次へ] を **クリックします**。

   - [設定 **] ページ** で、次の設定を構成します。
     - [添付 **ファイルが不明なマルウェアの安全な応答] セクションで、[** ブロック] を **選択します**。
     - [添付ファイル **のリダイレクト] セクション** で、[リダイレクトを有効にする **] オプションを選択します**。 検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターの電子メール アドレスを指定します。

     [ **次へ**] をクリックします。

3. [適用先] ページ **で**、[条件の追加]をクリックし、[適用する場合] を選択します。[受信者ドメイン] をクリックし、[追加] をクリックして、ドメインまたはドメインを選択し、[**追加**] をクリックし、[完了] をクリックし、[次へ] をクリックします。  

4. 設定を確認し、[完了] を **クリックします**。

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for microsoft Defender for Office 365

セーフ リンクを [設定するには](safe-links.md)、セーフ リンクのグローバル設定を確認および編集し、少なくとも 1 つのセーフ リンク ポリシーを作成します。

1. [セキュリティ & コンプライアンス センター][で、[](https://protection.office.com)脅威 **管理** ポリシー ATP セーフ リンク] を選択し、[グローバル設定] をクリックし、次の \>  \> 設定を構成します。

   - [ **安全なリンクを使用する] Office 365** アプリケーションがオンになっていることを確認する: ![ トグルオン ](../../media/scc-toggle-on.png) です。
   - **ユーザーが [安全なリンク] をクリック** しても追跡しない : この設定をオフにすると、ユーザーのクリックを追跡できます。オフ ![ に切り替えます ](../../media/scc-toggle-off.png) 。
   - **ユーザーが元の URL への安全なリンク** をクリックさせない : この設定がオンになっていることを確認する: ![ トグルオン ](../../media/scc-toggle-on.png) 。

   完了したら、**[保存]** をクリックします。

2. メインの [安全なリンク] ページに戻り、[作成] を **クリックします**。

3. 表示される **[安全なリンクの作成]** ポリシー ウィザードで、次の設定を構成します。

   - [名前 **] ボックス** に名前を入力し、[次 `Safe Links` へ] **をクリックします**。

   - [設定 **] ページ** で、次の設定を構成します。
     - **メッセージ内の不明な潜在的に悪意のある URL のアクションを選択します**。[オン] を **選択します**。
     - **Microsoft Teams 内の不明な URL または潜在的に** 悪意のある URL のアクションを選択します。[オン] を **選択します**。
     - **組織内で送信された電子メール メッセージへの安全なリンクを適用する**
     - **メッセージを配信する前に URL のスキャンが完了するのを待ちます**
     - **組織内で送信された電子メール メッセージへの安全なリンクを適用する**
     - **ユーザーに元の URL へのクリックを許可しない**

     [ **次へ**] をクリックします。

4. [適用先] ページ **で**、[条件の追加]をクリックし、[適用する場合] を選択します。[受信者ドメイン] をクリックし、[追加] をクリックして、ドメインまたはドメインを選択し、[**追加**] をクリックし、[完了] をクリックし、[次へ] をクリックします。  

5. 設定を確認し、[完了] を **クリックします**。

詳細については、「[安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)」をご覧ください。

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>パート 5 - SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルが有効になっていることを確認する

SharePoint、OneDrive、Teams のようなワークロードは、コラボレーションのために構築されています。 Defender for Office 365 は、チーム サイトやドキュメント ライブラリで悪意のあるファイルとして識別されるファイルをブロックおよび検出するのに役立ちます。 その動作の詳細については、こちらを参照 [してください](mdo-for-spo-odb-and-teams.md)。

> [!IMPORTANT]
> **この手順を開始する前に、Microsoft 365** 環境で監査ログが既に有効になっていることを確認してください。 これは通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。 詳細については、「監査ログ検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。

1. セキュリティ コンプライアンス [センターで、[脅威&](https://protection.office.com)ポリシー  ATP の安全な添付ファイル] を選択し、[ \>  \> グローバル設定]**をクリックします**。

2. **[SharePoint、OneDrive、および Microsoft Teams Office 365** の Defender を有効にする] トグルが右側にあるのを確認します。オンに切り替え、[ ![ 保存] を ](../../media/scc-toggle-on.png) **クリックします**。

3. 組織の安全な添付ファイル ポリシーとセーフ リンク[](set-up-safe-attachments-policies.md)ポリシーを確認 (および必要に応じて編集)[します](set-up-safe-links-policies.md)。

4. (推奨)グローバル管理者または SharePoint Online 管理者として _、DisallowInfectedFileDownload_ パラメーターをに設定して **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを実行します `$true` 。

   - `$true` 検出されたファイルのすべてのアクション (削除を除く) をブロックします。 検出されたファイルを開いたり、移動したり、コピーしたり、共有したりすることはできません。
   - `$false` 削除とダウンロードを除くすべてのアクションをブロックします。 ユーザーはリスクを受け入れ、検出されたファイルをダウンロードできます。

   > [!TIP]
   > Microsoft 365 で PowerShell を使用する方法の詳細については [、「Manage Microsoft 365 with PowerShell」を参照してください](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)。

5. 変更がすべての Microsoft 365 データセンターに分散するには、最大 30 分かかります。

### <a name="now-set-up-alerts-for-detected-files"></a>検出されたファイルのアラートを設定する

SharePoint Online、OneDrive for Business、または Microsoft Teams のファイルが悪意のあるファイルとして識別された場合に通知を受け取る場合は、アラートを設定できます。

1. [セキュリティ 管理 [] コンプライアンス &で、[](https://protection.office.com)アラートの管理 **]** \> **を選択します**。

2. [新 **しいアラート ポリシー] を選択します**。

3. アラートの名前を指定します。 たとえば、「ライブラリ」に「悪意のあるファイル」と入力できます。

4. アラートの説明を入力します。 たとえば、「SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが検出された場合に管理者に通知する」と入力できます。

5. [この **アラートをいつ送信....] セクションで** 、次の値を設定します。

   a. [アクティビティ] **リストで** 、[ファイル内 **の検出されたマルウェア] を選択します**。

   b. [ユーザー] **フィールドは** 空のままにします。

6. [このアラート **を送信する....]** セクションで、悪意のあるファイルが検出された場合に通知を受け取る必要がある 1 つ以上のグローバル管理者、セキュリティ管理者、またはセキュリティ リーダーを選択します。

7. **保存 .**

アラートの詳細については、「セキュリティ コンプライアンス センターでアクティビティアラートを作成する [&する」を参照してください](../../compliance/create-activity-alerts.md)。

> [!NOTE]
> 構成が完了したら、次のリンクを使用してワークロード調査を開始します。
>
>- [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)
>- [セキュリティ コンプライアンス センターを&検疫済みファイルを管理する](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが見つかった場合の操作](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Microsoft 365 で検疫済みメッセージとファイルを管理者として管理する](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>パート 6 - 構成する追加の設定

マルウェア、悪意のある URL とファイル、フィッシング、スパムからの保護を構成するとともに、0 時間の自動削除を構成することをお勧めします。

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>EOP の電子メールの 0 時間自動削除

[ゼロ時間自動削除](zero-hour-auto-purge.md) (ZAP) は、EOP を含むサブスクリプションで [使用できます](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。 この保護は既定でオンになっています。ただし、保護が有効になるには、次の条件を満たしている必要があります。

- スパムアクションは、スパム **対策ポリシーの [メッセージを迷惑** メール フォルダーに移動 [する] に設定されています](anti-spam-protection.md)。

- ユーザーは既定の迷惑メール設定 [を保持](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)し、迷惑メール保護を無効にしていない。

詳細については、「ゼロ時間自動削除 - スパムとマルウェアに対 [する保護」を参照してください](zero-hour-auto-purge.md)。

## <a name="post-setup-tasks-and-next-steps"></a>セットアップ後のタスクと次の手順

脅威保護機能を構成したら、それらの機能の動作を監視してください。 必要な操作を行うポリシーを確認して修正します。 また、価値を追加できる新機能やサービス更新プログラムを監視します。

****

|操作|追加情報|
|---|---|
|レポートを表示して、組織の脅威保護機能がどのように機能しているのか確認する|[セキュリティ ダッシュボード](security-dashboard.md) <p> [電子メール セキュリティ レポート](view-email-security-reports.md) <p> [Microsoft Defender for Office 365](view-reports-for-mdo.md) <p> [脅威エクスプローラー](threat-explorer.md)|
|必要に応じて、脅威保護ポリシーを定期的に確認および修正する|[セキュリティ スコア](../defender/microsoft-secure-score.md) <p> [スマート レポートと分析情報](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 の脅威の調査と対応の機能](./office-365-ti.md)|
|新機能とサービス更新プログラムを監視する|[標準リリースオプションとターゲット リリース オプション](../../admin/manage/release-options-in-office-365.md) <p> [Message Center](../../admin/manage/message-center.md) <p> [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [サービスの説明](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|EOP および Defender の推奨される Standard および Strict セキュリティ構成の詳細については、「365」Officeしてください。|[EOP と Microsoft Defender の 365 セキュリティOffice設定](recommended-settings-for-eop-and-office365.md)|
