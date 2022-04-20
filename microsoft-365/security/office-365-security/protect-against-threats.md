---
title: Microsoft Defender for Office 365、マルウェア対策、フィッシング詐欺対策、スパム対策、セーフ リンク、セーフ添付ファイル、ゼロ時間自動消去 (ZAP)、MDO セキュリティ構成の脅威から保護する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
ms.date: 06/22/2021
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、Microsoft 365で脅威の保護について学習し、組織で使用する方法を構成できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d067035d5eaf3c7a4febac6feeab0c56cd707728
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64941437"
---
# <a name="protect-against-threats"></a>脅威から保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Defender for Office 365の構成をチャンクに分割するクイック スタート ガイドを次に示します。 Office 365の脅威保護機能を初めて使用する場合、どこから始めるかがわからない場合、または実行することで最適な学習を *行う* 場合は、このガイダンスをチェックリストと開始点として使用します。

> [!IMPORTANT]
> **初期推奨設定はポリシーの種類ごとに含まれていますが、多くのオプションを使用でき、特定の組織のニーズに合わせて設定を調整できます**。 ポリシーまたは変更がデータセンターを通じて動作するには、約 30 分かかります。
>
> Defender for Office 365のほとんどのポリシーの手動構成をスキップするには、Standard または Strict レベルで事前設定されたセキュリティ ポリシーを使用できます。 詳細については、「[EOP とMicrosoft Defender for Office 365の事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。

## <a name="requirements"></a>要件

### <a name="subscriptions"></a>サブスクリプション

脅威保護機能 *はすべての* Microsoft またはOffice 365 サブスクリプションに含まれていますが、一部のサブスクリプションには高度な機能があります。 次の表に、この記事に含まれる保護機能と最小サブスクリプション要件を示します。

> [!TIP]
> 監査を有効にする手順を超 *えて、Office 365 Exchange Online Protection* (**EOP**) の一部としてマークされているマルウェア対策、フィッシング詐欺対策、スパム対策を開始します。 これは、Defender for Office 365記事では、(**Defender for Office 365**) EOP が含まれ、ビルドされるまで、奇妙に見える可能性があります。

|保護の種類|サブスクリプションの要件|
|---|---|
|監査ログ (レポート目的)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|マルウェア対策保護|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|フィッシング対策保護|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|スパム対策保護|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|電子メールおよびOfficeドキュメント内の悪意のある URL とファイルからの保護 (セーフ リンクと添付ファイルセーフ)|[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>ロールと権限

Defender for Office 365 ポリシーを構成するには、適切なロールが割り当てられている必要があります。 これらのアクションを実行できるロールについては、次の表を参照してください。

|役割または役割グループ|詳細を確認する場所|
|---|---|
|グローバル管理者|[Microsoft 365 管理者ロールについて](../../admin/add-users/about-admin-roles.md)|
|セキュリティ管理者|[組み込みロールをAzure ADする](/azure/active-directory/roles/permissions-reference#security-administrator)
|Exchange Online 組織の管理|[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)|

詳細については、[Microsoft 365 Defender ポータルのアクセス許可に関するページを](permissions-microsoft-365-security-center.md)参照してください。

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>レポートと調査のために監査ログを有効にする

- 監査ログを早期に開始します。 次の手順の一部では、監査を **オンにする** 必要があります。 監査ログは、[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)を含むサブスクリプションで使用できます。 脅威保護レポート、 [電子メール セキュリティ](view-email-security-reports.md) レポート、 [エクスプローラー](threat-explorer.md)でデータを表示するには、監査ログを *オンにする* 必要があります。 詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」を参照してください。

## <a name="part-1---anti-malware-protection-in-eop"></a>パート 1 - EOP でのマルウェア対策の保護

マルウェア対策の推奨設定の詳細については、「 [EOP マルウェア対策ポリシーの設定](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)」を参照してください。

1. Microsoft 365 Defender ポータルの [**マルウェア対策**] ページを開きます<https://security.microsoft.com/antimalwarev2>。

2. [ **マルウェア対策** ] ページで、名前をクリックして **既定 (既定値)** という名前のポリシーを選択します。

3. 開いたポリシーの詳細ポップアップで、[ **保護設定の編集]** をクリックし、次の設定を構成します。
   - **[保護の設定]** セクション:
     - **一般的な添付ファイル フィルターを有効にする**: 選択 (オン) します。 **[ファイルの種類のカスタマイズ**] をクリックして、さらにファイルの種類を追加します。
     - **マルウェアに対して 0 時間の自動消去を有効にする**: この設定が選択されていることを確認します。 マルウェアの ZAP の詳細については、マルウェアの [ゼロ時間自動消去 (ZAP)](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware) に関するページを参照してください。
   - **検疫ポリシー**: 既定値の AdminOnlyAccessPolicy を選択したままにします。 検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作と、ユーザーが検疫通知を受け取るかどうかを定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。
   - **[通知** ] セクション: 通知設定が選択されていないことを確認します。

   完了したら、**[保存]** をクリックします。

4. ポリシーの詳細ポップアップに戻り、**[閉じる]** をクリックします。

マルウェア対策ポリシーを構成する手順の詳細については、「 [EOP でのマルウェア対策ポリシーの構成](configure-anti-malware-policies.md)」を参照してください。

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>パート 2 - EOP とDefender for Office 365でのフィッシング対策の保護

[フィッシング対策保護](anti-phishing-protection.md) は、 [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) を含むサブスクリプションで使用できます。 高度なフィッシング対策保護は[、Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)で利用できます。

フィッシング対策ポリシーの推奨設定の詳細については、Microsoft Defender for Office 365の [EOP フィッシング対策ポリシー設定](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)と[フィッシング対策ポリシーの設定に関するページを](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)参照してください。

次の手順では、既定のフィッシング対策ポリシーを構成する方法について説明します。 Defender for Office 365でのみ使用できる設定は、明確にマークされます。

1. Microsoft 365 Defender ポータルの [**フィッシング対策**] ページを開きます<https://security.microsoft.com/antiphishing>。

2. [ **フィッシング対策** ] ページで、名前をクリックして **Office365 AntiPhish Default (既定値)** という名前のポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップで、次の設定を構成します。
   - **[フィッシングのしきい値&保護** ] セクション: [ **保護設定の編集]** をクリックし、ポップアップで次の設定を構成します。
     - **フィッシングメールのしきい値**<sup>\*</sup>: **[2 - 攻撃的 (** 標準)] または **[3 - より積極的な** (厳密)] を選択します。
     - **[偽装** ] セクション <sup>\*</sup>: 次の値を構成します。
       - [ **ユーザーの保護を有効にする**] を選択し、表示される **[Manage (nn) sender(s)]** リンクをクリックし、組織のボード メンバー、CEO、CFO、その他の上級リーダーなどの偽装から保護するために内部および外部の送信者を追加します。
       - [ **保護するドメインを有効にする**] を選択し、表示される次の設定を構成します。
         - [ **自分の所有するドメインを含める** ] を選択して、承認済みドメインの内部送信者を保護します ([ **自分のドメインの表示**] をクリックして表示されます)。
         - 他のドメインの送信者を保護するには、[ **カスタム ドメインを含める**] を選択し、表示される **[管理 ( nn) カスタム ドメイン]** リンクをクリックし、偽装から保護する他のドメインを追加します。
     - **[信頼できる送信者とドメインの追加** ] セクション <sup>\*</sup>: [ **信頼された送信者とドメインの管理] を** クリックして、必要に応じて偽装保護に送信者と送信者のドメインの例外を構成します。
     - メールボックス インテリジェンスの設定 <sup>\*</sup>: [ **メールボックス インテリジェンスを有効にする]** と **[偽装保護のインテリジェンスを有効にする]** が選択されていることを確認します。
     - **[スプーフィング** ] セクション: **[スプーフィング インテリジェンスを有効にする]** が選択されていることを確認します。

     完了したら、**[保存]** をクリックします。

   - **[アクション]** セクション: [ **アクションの編集]** をクリックし、ポップアップで次の設定を構成します。
     - **[メッセージ アクション]** セクション: 次の設定を構成します。
       - 偽装されたユーザー <sup>\*</sup>**としてメッセージが検出された場合**: **[メッセージの検疫]** を選択します。 [ **検疫ポリシーの適用** ] ボックスが表示され、ユーザー偽装保護によって検疫されたメッセージに適用される [検疫ポリシー](quarantine-policies.md) を選択します。
       - **偽装されたドメインとしてメッセージが検出された場合は**、[**メッセージの検疫**] を選択します。<sup>\*</sup> **[検疫ポリシーの適用**] ボックスが表示され、ドメイン偽装保護によって検疫されたメッセージに適用される [検疫ポリシー](quarantine-policies.md)を選択します。
       - **メールボックス インテリジェンスで偽装されたユーザー**<sup>\*</sup>が検出された場合: [ **メッセージを受信者の迷惑メール フォルダーに移動** する (標準)] または [ **メッセージの検疫** (Strict)] を選択します。 **[検疫] を** 選択すると、[**検疫ポリシーの適用**] ボックスが表示され、メールボックス インテリジェンス保護によって検疫されたメッセージに適用される [検疫ポリシー](quarantine-policies.md)が選択されます。
       - **メッセージがスプーフィングとして検出された場合**: **[メッセージを受信者の迷惑メール フォルダーに移動** する (標準)] または **[メッセージの検疫** (Strict)] を選択します。  **[検疫] を** 選択すると、[**検疫ポリシーの適用**] ボックスが表示され、スプーフィング インテリジェンス保護によって検疫されたメッセージに適用される [検疫ポリシー](quarantine-policies.md)が選択されます。
     - **[インジケーター&安全に関するヒント** ] セクション: 次の設定を構成します。
       - **最初の連絡先安全性のヒントを表示** する: 選択 (オン) します。
       - **ユーザー権限借用安全性のヒント**<sup>\*</sup>を表示する: 選択 (オン) します。
       - **ドメイン権限借用安全性のヒント**<sup>\*</sup>を表示する: 選択 (オン) します。
       - **ユーザー権限借用の通常とは異なる文字を表示安全性のヒント**<sup>\*</sup>: 選択 (オン) します。
       - **スプーフィング用の認証されていない送信者の表示 (?)** : 選択 (オン) します。
       - **"via" タグを表示** する: 選択 (オン) します。

     完了したら、**[保存]** をクリックします。

   <sup>\*</sup>この設定は、Defender for Office 365でのみ使用できます。

4. [**保存] を** クリックし、[**閉じる**] をクリックします。

フィッシング対策ポリシーを構成する手順の詳細については、「[EOP でフィッシング対策ポリシーを構成](configure-anti-phishing-policies-eop.md)する」と「[Microsoft Defender for Office 365でフィッシング対策ポリシーを構成する](configure-mdo-anti-phishing-policies.md)」を参照してください。

## <a name="part-3---anti-spam-protection-in-eop"></a>パート 3 - EOP でのスパム対策の保護

スパム対策の推奨設定の詳細については、「 [EOP スパム対策ポリシーの設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)」を参照してください。

1. Microsoft 365 Defender ポータルの [**スパム対策ポリシー**] ページを開きます<https://security.microsoft.com/antispam>。

2. [ **スパム対策ポリシー** ] ページで、名前をクリックして、一覧から **スパム対策受信ポリシー (既定)** という名前のポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップで、次の設定を構成します。
   - **[一括メールのしきい値&スパムのプロパティ** ] セクション: [ **スパムのしきい値とプロパティの編集]** をクリックします。 表示されるポップアップで、次の設定を構成します。
     - **一括メールのしきい値**: この値を 5 (Strict) または 6 (Standard) に設定します。
     - 他の設定は既定値のままにします (**オフ** または **なし**)。

     完了したら、**[保存]** をクリックします。

   - **[アクション]** セクション: [ **アクションの編集]** をクリックします。 表示されるポップアップで、次の設定を構成します。
     - **[メッセージ アクション]** セクション:
       - **スパム**: [ **迷惑メールへのメッセージの移動] フォルダー** が選択されていることを確認します (標準) か、[ **検疫メッセージ** ] ([厳格] ) を選択します。
       - **信頼度の高いスパム**: **[検疫メッセージ]** を選択します。
       - **フィッシング**: [ **検疫メッセージ]** を選択します。
       - **高信頼フィッシング**: **検疫メッセージ** が選択されていることを確認します。
       - **一括**: **[メッセージを迷惑メールフォルダーに移動する** ] が選択されていることを確認します (標準) か、[ **検疫メッセージ** ( Strict)] を選択します。

       **[検疫メッセージ**] を選択するアクションごとに、[**検疫ポリシーの選択**] ボックスが表示され、スパム対策によって検疫されたメッセージに適用される [検疫ポリシー](quarantine-policies.md)が選択されます。

     - **この数日間、検疫でスパムを保持** する: **値を 30** 日間確認します。
     - **スパムの安全性に関するヒントを有効にする**: この設定が選択されていることを確認します (オン)。
     - **ゼロ時間自動消去 (ZAP) を有効にする**: この設定が選択されていることを確認します (オン)。
       - **フィッシング メッセージを有効にする**: この設定が選択されていることを確認します (オン)。 詳細については、「 [フィッシングのゼロ時間自動消去 (ZAP)」を](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing)参照してください。
       - **スパム メッセージに対して有効にする**: この設定が選択されていることを確認します (オン)。 詳細については、「スパムの [ゼロ時間自動消去 (ZAP)」を](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam)参照してください。

     完了したら、**[保存]** をクリックします。

   - **[許可およびブロックされた送信者とドメイン** ] セクション: [EOP でのブロックされた送信者リストの作成または EOP での差出人セーフ リストの作成](create-block-sender-lists-in-office-365.md) に関するページの説明に従って、許可された送信者と許可されたドメインを確認または編集 [します](create-safe-sender-lists-in-office-365.md)。

     完了したら、**[保存]** をクリックします。

4. 完了したら、**[閉じる]** をクリックします。

スパム対策ポリシーを構成する手順の詳細については、「 [EOP でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>パート 4 - 悪意のある URL とファイルからの保護 (Defender for Office 365のリンクとセーフ添付ファイルセーフ)

悪意のある URL とファイルからのクリック時間の保護は、[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)を含むサブスクリプションで利用できます。 [これは、セーフ添付ファイル](safe-attachments.md)ポリシーと [セーフ リンク](safe-links.md) ポリシーを使用して設定されます。

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365で添付ファイル ポリシーをセーフする

セーフ添付ファイルの推奨設定の詳細については、「.[添付ファイルの設定をセーフします](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。

1. Microsoft 365 Defender ポータルの **[セーフ添付ファイル**] ページを開きます<https://security.microsoft.com/safeattachmentv2>。

2. **[セーフ添付ファイル**] ページで、[**グローバル設定**] をクリックし、表示されるポップアップで次の設定を構成します。
   - **SharePoint、OneDrive、およびMicrosoft TeamsのDefender for Office 365を有効にする**: この設定をオンにします (![オンに](../../media/scc-toggle-on.png)切り替えます)。

     > [!IMPORTANT]
     > **SharePoint、OneDrive、Microsoft Teamsの添付ファイルをセーフする前に、組織で監査ログが有効になっていることを確認します**。 通常、このアクションは、Exchange Onlineで監査ログ ロールが割り当てられているユーザーによって実行されます。 詳細については、「 [監査ログ検索のオンとオフを切り替える](../../compliance/turn-audit-log-search-on-or-off.md)」を参照してください。

   - **Office クライアントのドキュメントセーフオンにする**: この設定をオンにします (![オンに](../../media/scc-toggle-on.png)切り替えます)。 この機能は、必要な種類のライセンスでのみ使用でき、意味があることに注意してください。 詳細については、「[Microsoft 365 E5のドキュメントのセーフ](safe-docs.md)」を参照してください。
   - **ドキュメントセーフファイルが悪意のあるものとして識別された場合でも、ユーザーが保護されたビューをクリックできるようにします**。この設定がオフになっていることを確認します (![トグル オフ)。](../../media/scc-toggle-off.png)。

   完了したら、[保存] をクリック **します**。

3. **[セーフ添付ファイル**] ページに戻り、[作成] アイコンをクリックします![](../../media/m365-cc-sc-create-icon.png)。

4. 開 **いたセーフ添付ファイルの作成ポリシー** ウィザードで、次の設定を構成します。
   - **ポリシー ページに名前を付** けます。
     - **名前**: 一意でわかりやすい内容を入力します。
     - **説明**: 省略可能な説明を入力します。
   - **[ユーザーとドメイン]** ページ: これは最初のポリシーであり、カバレッジを最大化する可能性が高いため、[**ドメイン**] ボックスに [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)を入力することを検討してください。 それ以外の場合は、[ **ユーザー** と **グループ]** ボックスを使用して、より詳細な制御を行うことができます。 例外を指定するには **、[これらのユーザー、グループ、ドメインを除外する** ] を選択し、値を入力します。
   - **設定** ページ:
     - **セーフ 添付ファイル不明のマルウェア応答**: **[ブロック**] を選択します。
     - **検疫ポリシー**: 既定値は空白です。つまり、AdminOnlyAccessPolicy ポリシーが使用されます。 検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作と、ユーザーが検疫通知を受け取るかどうかを定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。
     - **検出された添付ファイルをリダイレクト** する : **リダイレクトを有効にする**: この設定をオン (選択) にして、検出されたメッセージを受信する電子メール アドレスを入力します。
     - **スキャンが完了できない場合はセーフ添付ファイル検出応答を適用します (タイムアウトまたはエラー)**:この設定が選択されていることを確認します。

5. 完了したら、[ **送信]** をクリックし、[完了] をクリック **します**。

6. (推奨)グローバル管理者または SharePoint Online 管理者として、SharePoint Online PowerShell で _DisallowInfectedFileDownload_ パラメーターを設定して **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを`$true`実行します。
   - `$true` は、検出されたファイルに対するすべてのアクション (削除を除く) をブロックします。 検出されたファイルを開いたり、移動したり、コピーしたり、共有したりすることはできません。
   - `$false` は、削除とダウンロードを除くすべてのアクションをブロックします。 ユーザーはリスクを受け入れ、検出されたファイルをダウンロードすることを選択できます。

7. 変更がすべてのMicrosoft 365データセンターに分散されるまでに最大 30 分かかります。

セーフ添付ファイル ポリシーとセーフ添付ファイルのグローバル設定を構成する手順の詳細については、次のトピックを参照してください。

- [Microsoft Defender for Office 365でセーフ添付ファイル ポリシーを設定する](set-up-safe-attachments-policies.md)
- [SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする](turn-on-mdo-for-spo-odb-and-teams.md)
- [Microsoft 365 E5 の安全なドキュメント](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365でリンク ポリシーをセーフする

セーフ リンクの推奨設定の詳細については、「セーフ [リンクの設定](recommended-settings-for-eop-and-office365.md#safe-links-settings)」を参照してください。

1. Microsoft 365 Defender ポータル<https://security.microsoft.com/safelinksv2>の **[セーフ リンク**] ページを開きます。

2. **[セーフ リンク**] ページで、[**グローバル設定**] をクリックし、表示されるポップアップで次の設定を構成します。
   - **サポートされているOffice 365 アプリセクションのコンテンツに適用される設定**:
     - **Office 365 アプリで セーフ リンクを使用** する: この設定がオンになっていることを確認します (![オンに切り替えます)。](../../media/scc-toggle-on.png)。
     - **ユーザーがOffice 365 アプリで保護されたリンクをクリックした時点を追跡しないでください**。この設定をオフにします (![オフに切り替えます)。](../../media/scc-toggle-off.png)。
     - **ユーザーがOffice 365 アプリで元の URL をクリック** できないようにする:この設定がオンになっていることを確認します (![オンに切り替えます)。](../../media/scc-toggle-on.png)。

   完了したら、[保存] をクリック **します**。

3. **[セーフ リンク**] ページに戻り、[作成] アイコンをクリックします![](../../media/m365-cc-sc-create-icon.png)。

4. 開いた **セーフ リンクの作成ポリシー** ウィザードで、次の設定を構成します。
   - **ポリシー ページに名前を付** けます。
     - **名前**: 一意でわかりやすい内容を入力します。
     - **説明**: 省略可能な説明を入力します。
   - **[ユーザーとドメイン]** ページ: これは最初のポリシーであり、カバレッジを最大化する可能性が高いため、[**ドメイン**] ボックスに [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)を入力することを検討してください。 それ以外の場合は、[ **ユーザー** と **グループ]** ボックスを使用して、より詳細な制御を行うことができます。 例外を指定するには **、[これらのユーザー、グループ、ドメインを除外する** ] を選択し、値を入力します。
   - **Url & [保護設定] ページをクリックします** 。
     - **[電子メール] セクション内の潜在的に悪意のある URL に対するアクション** :
       - **オン: セーフ リンクは、ユーザーが電子メールでリンクをクリックしたときに既知の悪意のあるリンクの一覧をチェックします**。設定を選択します (オン)。
       - **組織内で送信されたメール メッセージに セーフ リンクを適用** する: この設定を選択します (オン)。
       - **ファイルを指す不審なリンクとリンクのリアルタイム URL スキャンを適用** する:この設定を選択します (オン)。
       - **メッセージを配信する前に URL スキャンが完了するのを待ちます**。この設定を選択します (オン)。
       - **URL を書き換えないでください。セーフ Links API を使用してチェックを実行してください**。この設定が選択されていない (オフにする) ことを確認します。
     - **電子メールで次の URL を書き換えないでください**。この設定に関する具体的な推奨事項はありません。 詳細については、[セーフ リンク ポリシーの「次の URL を書き換えない」の一覧](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)を参照してください。
     - **Microsoft Teams セクションの潜在的に悪意のある URL に対するアクション**:
       - ***オン: セーフ リンクは、ユーザーがMicrosoft Teamsでリンクをクリックしたときに既知の悪意のあるリンクの一覧をチェックします**。この設定を選択します (オン)。
     - **[保護設定] セクションをクリックします** 。
       - **ユーザーのクリックを追跡する**: この設定が選択されていることを確認します (オン)。
       - **ユーザーが元の URL までクリックできるようにする**:この設定をオフにします (選択されていません)。
       - **通知ページと警告ページに組織のブランドを表示** する: この設定を選択する (オンにする) は、組織のロゴをアップロードするための [Microsoft 365テーマのカスタマイズ](../../admin/setup/customize-your-organization-theme.md)に関するページの手順に従った後でのみ意味があります。
   - **[通知]** ページ:
     - **ユーザーに通知する方法** セクション: 必要に応じて、[ **カスタム通知テキストを使用** する] を選択して、使用するカスタマイズされた通知テキストを入力できます。 [**自動ローカライズにMicrosoft 翻訳ツールを使用** する] を選択して、カスタム通知テキストをユーザーの言語に翻訳することもできます。 それ以外の場合は、 **既定の通知テキストを選択** したままにします。

5. 完了したら、[ **送信]** をクリックし、[完了] をクリック **します**。

セーフ リンクのセーフ リンク ポリシーとグローバル設定を構成する手順の詳細については、次のトピックを参照してください。

- [Microsoft Defender for Office 365 で安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)
- [Microsoft Defender for Office 365で セーフ リンクのグローバル設定を構成する](configure-global-settings-for-safe-links.md)

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a>これで、SharePoint Online または OneDrive for Businessで検出されたファイルのアラートを設定します

SharePoint Online またはOneDrive for Businessのファイルが悪意のあるファイルとして識別されたときに通知を受け取るには、このセクションで説明するようにアラートを設定できます。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**電子メール & コラボレーション** \> **ポリシー&ルール** \> **アラート ポリシー**] に移動します。

2. [ **アラート ポリシー** ] ページで、[ **新しいアラート ポリシー**] をクリックします。

3. **新しいアラート ポリシー** ウィザードが開きます。 [ **名前]** ページで、次の設定を構成します。
   - **名前**: 一意でわかりやすい名前を入力します。 たとえば、「ライブラリ」に「悪意のあるファイル」と入力できます。
   - **説明**: 省略可能な説明を入力します。
   - **重大度**: **[低**]、[ **中]** 、または **[高]** を選択します。
   - **カテゴリ**: **[脅威の管理**] を選択します。

   完了したら、[**次へ**] をクリックします。

4. [ **アラート設定の作成]** ページで、次の設定を構成します。
   - アラートの対象 **は何ですか?** セクション: **アクティビティは、** \> **ファイル内のマルウェアが検出されました**。
   - **[アラートをトリガーする方法** ] セクション: アクティビティがルールと **一致するたびに** 選択されていることを確認します。

   完了したら、[**次へ**] をクリックします。

5. [ **受信者の設定] ページで** 、次の設定を構成します。
   - **電子メール通知の送信**: この設定が選択されていることを確認します。
   - **電子メール受信者**: 悪意のあるファイルが検出されたときに通知を受け取る必要がある 1 人以上のグローバル管理者、セキュリティ管理者、またはセキュリティ 閲覧者を選択します。
   - **1 日の通知の制限**: **[制限なし]** が選択されていることを確認します。

   完了したら、[**次へ**] をクリックします。

6. [**設定の確認**] ページで、設定を確認し、[はい] を確認 **し、すぐにオンに** し、[**完了**] をクリックします。

アラート ポリシーの詳細については、 [Microsoft Purview コンプライアンス ポータルのアラート ポリシーに関するページを](../../compliance/alert-policies.md)参照してください。

> [!NOTE]
> 構成が完了したら、次のリンクを使用してワークロードの調査を開始します。
>
> - [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)
> - [Microsoft 365 Defender ポータルを使用して、Defender for Office 365で検疫されたファイルを管理する](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
> - [SharePoint Online、OneDrive、またはMicrosoft Teamsで悪意のあるファイルが見つかった場合の対処方法](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
> - [Microsoft 365で検疫済みのメッセージとファイルを管理者として管理する](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a>セットアップ後のタスクと次の手順

脅威保護機能を構成したら、これらの機能の動作を監視してください。 ポリシーを確認し、必要な操作を行えるように変更します。 また、付加価値を高めることができる新機能とサービスの更新も確認してください。

|操作|追加情報|
|---|---|
|レポートを表示して、組織の脅威保護機能がどのように機能しているかを確認する|[電子メール セキュリティ レポート](view-email-security-reports.md) <p> [Microsoft Defender for Office 365のレポート](view-reports-for-mdo.md) <p> [脅威エクスプローラー](threat-explorer.md)|
|必要に応じて、脅威保護ポリシーを定期的に確認して修正する|[セキュリティ スコア](../defender/microsoft-secure-score.md) <p> [Microsoft 365脅威の調査と対応機能](./office-365-ti.md)|
|新機能とサービスの更新を確認する|[標準リリースオプションとターゲット リリース オプション](../../admin/manage/release-options-in-office-365.md) <p> [Message Center](../../admin/manage/message-center.md) <p> [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [サービスの説明](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
