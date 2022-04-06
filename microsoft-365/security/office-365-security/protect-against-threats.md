---
title: Microsoft Defender for Office 365、マルウェア対策、フィッシング対策、スパム対策、セーフ リンク、セーフ 添付ファイル、ゼロ時間自動削除 (ZAP)、MDO セキュリティ構成の脅威から保護する
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
description: 管理者は、組織の脅威保護Microsoft 365、組織で使用する方法を構成できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5a0be5171a2de07792cd259dc6547046d7c1630
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507189"
---
# <a name="protect-against-threats"></a>脅威から保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

クイック スタート ガイドを次に示します。このクイック スタート ガイドは、Defender for Office 365構成を分割します。 Office 365 の脅威保護機能を初めから使用する場合は、どこから始めるのか分からず、最適な方法を学ぶ場合は、チェックリストと開始点としてこのガイダンスを使用してください。

> [!IMPORTANT]
> **初期推奨設定はポリシー** の種類ごとに含まれていますが、多くのオプションを使用できます。また、特定の組織のニーズに合わせて設定を調整することもできます。 ポリシーまたは変更がデータセンター経由で動作するには、約 30 分かかります。
>
> 標準または厳密なレベルで、Defender for Office 365ポリシーの手動構成をスキップするには、事前設定されたセキュリティ ポリシーを使用できます。 詳細については、「EOP および EOP のセキュリティ ポリシーを事前に設定[する」を参照Microsoft Defender for Office 365](preset-security-policies.md)。

## <a name="requirements"></a>Requirements

### <a name="subscriptions"></a>サブスクリプション

脅威保護機能は *、すべての Microsoft* または Office 365 サブスクリプションに含まれていますが、一部のサブスクリプションには高度な機能があります。 次の表に、この記事に含まれる保護機能と最小サブスクリプション要件を示します。

> [!TIP]
> 監査を有効にする指示を超えて、手順によってマルウェア対策、フィッシング対策、スパム対策が開始され、Office 365 Exchange Online Protection (**EOP**) の一部としてマークされます。 これは、EOP が含 **Defender for Office 365 (Defender for Office 365**) が含まれるまで、この記事では奇妙に思えます。

|保護の種類|サブスクリプションの要件|
|---|---|
|監査ログ (レポート用)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|マルウェア対策保護|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|フィッシング対策保護|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|スパム対策保護|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|電子メールおよびドキュメント内の悪意のある URL やファイルOffice保護 (セーフ リンクセーフ添付ファイル)|[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>ロールと権限

ポリシーをDefender for Office 365するには、適切な役割を割り当てる必要があります。 これらのアクションを実行できるロールについては、以下の表を参照してください。

|役割または役割グループ|詳細については、次の情報を参照してください。|
|---|---|
|グローバル管理者|[Microsoft 365 管理者ロールについて](../../admin/add-users/about-admin-roles.md)|
|セキュリティ管理者|[Azure AD組み込みの役割](/azure/active-directory/roles/permissions-reference#security-administrator)
|Exchange Online 組織の管理|[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)|

詳細については、「Microsoft 365 Defender [ポータルのアクセス許可」を参照してください](permissions-microsoft-365-security-center.md)。

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>レポートと調査の監査ログを有効にする

- 監査ログを早期に開始します。 次の手順の一部について **、監査を ON** にする必要があります。 監査ログは、監査ログを含むサブスクリプション[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)。 脅威保護レポート、電子メール セキュリティ レポート、エクスプローラー [](view-email-security-reports.md)でデータを表示するには [](threat-explorer.md)、監査ログをオンにする必要 *があります*。 詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」を参照してください。

## <a name="part-1---anti-malware-protection-in-eop"></a>パート 1 - EOP のマルウェア対策保護

マルウェア対策の推奨設定の詳細については、「EOP マルウェア対策ポリシー [設定」を参照してください](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)。

1. [マルウェア対策 **] ポータルの** [マルウェア対策] Microsoft 365 Defenderを開きます<https://security.microsoft.com/antimalwarev2>。

2. [マルウェア対策 **] ページで** 、名前をクリックして **Default (Default)** という名前のポリシーを選択します。

3. 開くポリシーの詳細フライアウトで、[保護設定の編集] を **クリック** し、次の設定を構成します。
   - **[保護の設定** ] セクション:
     - **共通の添付ファイル フィルターを有効にする**: 選択 (オン) します。 [ファイル **の種類のカスタマイズ] を** クリックして、ファイルの種類を追加します。
     - **マルウェアに対して 0 時間自動削除を有効にする**: この設定が選択されているのを確認します。 マルウェアの ZAP の詳細については、「マルウェアの [ゼロ時間自動削除 (ZAP)」を参照してください](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware)。
   - **検疫ポリシー**: 既定値 AdminOnlyAccessPolicy を選択したままにします。 検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作と、ユーザーが検疫通知を受け取るかどうかを定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。
   - **[通知** ] セクション: 通知設定が選択されなかからなか確認します。

   完了したら、**[保存]** をクリックします。

4. ポリシーの詳細ポップアップに戻り、**[閉じる]** をクリックします。

マルウェア対策ポリシーを構成する手順の詳細については、「EOP でマルウェア対策ポリシーを構成する」 [を参照してください](configure-anti-malware-policies.md)。

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>パート 2 - EOP とアプリのフィッシング対策Defender for Office 365

[フィッシング対策保護は、](anti-phishing-protection.md) EOP を含むサブスクリプションで [利用できます](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。 高度なフィッシング対策保護は、[Defender for Office 365。](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

フィッシング対策ポリシーの推奨設定の詳細については、「[EOP](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) フィッシング対策ポリシー設定」および「フィッシング対策ポリシー設定」を参照[Microsoft Defender for Office 365。](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)

次の手順では、既定のフィッシング対策ポリシーを構成する方法について説明します。 設定でしか使用できないDefender for Office 365マークが付いている。

1. [フィッシング **対策] ページを** [Microsoft 365 Defender] で開きます<https://security.microsoft.com/antiphishing>。

2. [フィッシング **対策] ページで** 、名前をクリックして **Office365 AntiPhish Default (Default)** という名前のポリシーを選択します。

3. 表示されるポリシーの詳細フライアウトで、次の設定を構成します。
   - **[フィッシングの&保護** ] セクション **: [保護** 設定の編集] をクリックし、開くフライアウトで次の設定を構成します。
     - **フィッシングメールのしきい値**<sup>\*</sup>: **[2 - アグレッシブ** (標準) ] または **[3 - より攻撃** 的 (厳密] ) を選択します。
     - **[偽装]** セクション <sup>\*</sup>: 次の値を構成します。
       - [ユーザー **の** 保護を有効にする] を選択し、表示される [送信者の管理 **] リンク** をクリックし、組織の役員、CEO、CFO、その他の上級リーダーなど、偽装から保護するために内部および外部の送信者を追加します。
       - [ **保護するドメインを有効にする] を** 選択し、表示される次の設定を構成します。
         - [ **自分が所有するドメインを含める** ] を選択して、受け入れドメイン内の内部送信者を偽装から保護します ([自分のドメインの **表示] を** クリックして表示されます)。
         - 他のドメインの送信者を保護するには、[カスタム ドメインを含める] を選択し、表示される [管理 **( nn)** カスタム ドメイン] リンクをクリックしてから、偽装から保護するために他のドメインを追加します。
     - **[信頼できる送信者**<sup>\*</sup>とドメインの追加] セクション: [管理] **(nn)** 信頼できる送信者とドメインをクリックして、必要に応じて送信者と送信者ドメインの例外を偽装保護に構成します。
     - メールボックス インテリジェンスの設定 <sup>\*</sup>: [メールボックス インテリジェンス **を有効にする] と** [偽装保護のインテリジェンスを有効にする] **が** 選択されています。
     - **[スプー** フィング] **セクション: [スプーフィング インテリジェンスを有効にする] が** 選択されているのを確認します。

     完了したら、**[保存]** をクリックします。

   - **[操作** ] セクション: [ **アクションの編集]** をクリックし、開くフライアウトで次の設定を構成します。
     - **[メッセージの操作** ] セクション: 次の設定を構成します。
       - **偽装ユーザーとしてメッセージが検出された場合**<sup>\*</sup>: [メッセージの **検疫] を選択します**。 [**検疫ポリシーの適用**] ボックスが表示され、[](quarantine-policies.md)ユーザー偽装保護によって検疫されるメッセージに適用される検疫ポリシーを選択します。
       - **偽装ドメインとしてメッセージが検出された場合**<sup>\*</sup>: [メッセージの **検疫] を選択します**。 [**検疫ポリシーの適用**] ボックスが表示され、[](quarantine-policies.md)ドメイン偽装保護によって検疫されるメッセージに適用される検疫ポリシーを選択します。
       - **メールボックス インテリジェンスが偽装ユーザーを**<sup>\*</sup>検出した場合: [メッセージを受信者の迷惑メール **フォルダー (標準** ) に移動する] または [メッセージを検疫 **する (厳密** ]) を選択します。 [メッセージの **検疫] を** 選択すると、[検疫ポリシーの適用] ボックスが表示され [](quarantine-policies.md)、メールボックス インテリジェンス保護によって検疫されるメッセージに適用される検疫ポリシーを選択します。
       - **メッセージがスプーフィングとして検出** された場合: [メッセージを受信者の迷惑メール **フォルダー (標準** ) に移動する] または [メッセージを検疫 **する (厳密** ]) を選択します。  [メッセージの **検疫] を** 選択すると、[検疫ポリシーの適用] ボックスが表示され [](quarantine-policies.md)、スプーフィング インテリジェンス保護によって検疫されるメッセージに適用される検疫ポリシーを選択します。
     - **[インジケーター&ヒント** : 次の設定を構成します。
       - **最初の連絡先を表示安全性のヒント**: 選択 (オン) します。
       - **[ユーザーの偽装を表示安全性のヒント**<sup>\*</sup>: 選択 (オン) します。
       - **[ドメインの偽装を表示安全性のヒント**<sup>\*</sup>: 選択 (オン) します。
       - **[ユーザー偽装の異常な文字を表示安全性のヒント**<sup>\*</sup>: 選択 (オンにする) をクリックします。
       - **スプーフィングの認証されていない** 送信者に対して表示 (?) する: 選択 (オン) します。
       - **"via" タグを表示する**: (オンにする) を選択します。

     完了したら、**[保存]** をクリックします。

   <sup>\*</sup>この設定は、Defender for Office 365 でのみ使用できます。

4. [保存 **] をクリック** し、[閉じる] を **クリックします。**

フィッシング対策ポリシーを構成する詳細な手順については、「[EOP](configure-anti-phishing-policies-eop.md) でフィッシング対策ポリシーを構成する」および「Microsoft Defender for Office 365 でフィッシング対策ポリシーを構成する[」を参照してください](configure-mdo-anti-phishing-policies.md)。

## <a name="part-3---anti-spam-protection-in-eop"></a>パート 3 - EOP のスパム対策保護

スパム対策の推奨設定の詳細については、「EOP スパム対策 [ポリシー設定」を参照してください](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。

1. [スパム **対策ポリシー] ページを** [Microsoft 365 Defender] で開きます<https://security.microsoft.com/antispam>。

2. [スパム **対策ポリシー]** ページで、名前をクリックして、リストからスパム対策受信ポリシー **(Default)** という名前のポリシーを選択します。

3. 表示されるポリシーの詳細フライアウトで、次の設定を構成します。
   - **[スパムのプロパティ] &メールの一括しきい値** : [スパムのしきい値 **とプロパティの編集] をクリックします**。 表示されるフライアウトで、次の設定を構成します。
     - **バルク メールのしきい** 値: この値を 5 (Strict) または 6 (Standard) に設定します。
     - 他の設定は既定値のままにします (**Off** または **None**)。

     完了したら、**[保存]** をクリックします。

   - **[アクション** ] セクション: [アクション **の編集] をクリックします**。 表示されるフライアウトで、次の設定を構成します。
     - **[メッセージの操作** ] セクション:
       - **スパム**: [メッセージ **を迷惑メール フォルダーに** 移動する] が選択されている (標準) を確認するか、[検疫メッセージ ] (Strict) **を** 選択します。
       - **高信頼スパム**: [検疫メッセージ **] を選択します**。
       - **フィッシング:** [検疫メッセージ **] を選択します**。
       - **信頼度の高いフィッシング**: [ **検疫メッセージ] が** 選択されているを確認します。
       - **一** 括: [ **メッセージを迷惑メール フォルダーに** 移動する] が選択されている (標準) を確認するか、[検疫メッセージ ] (Strict) **を** 選択します。

       [検疫メッセージ] を選択するアクションごとに、[検疫ポリシーの選択] ボックスが表示され、[](quarantine-policies.md)スパム対策保護によって検疫されたメッセージに適用される検疫ポリシーを選択します。

     - **この日数の検疫でスパムを保持** する: 値 **を 30 日間確認** します。
     - **[スパムの安全に関するヒント** を有効にする]: この設定が選択 (オン) になっていることを確認します。
     - **ゼロ時間自動削除 (ZAP)** を有効にする: この設定が選択 (オン) になっていることを確認します。
       - **フィッシング メッセージを有効にする**: この設定が選択 (オン) になっていることを確認します。 詳細については、「フィッシングの [ゼロ時間自動削除 (ZAP)」を参照してください](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing)。
       - **スパム メッセージを有効にする**: この設定が選択 (オン) になっていることを確認します。 詳細については、「スパムの [ゼロ時間自動削除 (ZAP)」を参照してください](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam)。

     完了したら、**[保存]** をクリックします。

   - **[許可** およびブロックされた送信者とドメイン] セクション: 「 [EOP](create-block-sender-lists-in-office-365.md) で受信拒否リストを作成する」または「 [EOP](create-safe-sender-lists-in-office-365.md) で差出人セーフ リストを作成する」の説明に従って、許可されている送信者と許可されたドメインを確認または編集します。

     完了したら、**[保存]** をクリックします。

4. 完了したら、**[閉じる]** をクリックします。

スパム対策ポリシーを構成する詳細な手順については、「EOP でスパム対策ポリシーを構成する」 [を参照してください](configure-your-spam-filter-policies.md)。

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>パート 4 - 悪意のある URL とファイルからの保護 (セーフリンクとセーフ添付ファイルDefender for Office 365)

悪意のある URL やファイルからのクリック時の保護は、悪意のある URL やファイルを含む[サブスクリプションMicrosoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。 [添付ファイルとリンク] [セーフポリシー](safe-attachments.md)セーフ[設定](safe-links.md)されます。

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>セーフの添付ファイル ポリシー Microsoft Defender for Office 365

添付ファイルの推奨設定の詳細については、「セーフ」を参照してください。[セーフ添付ファイルの設定。](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

1. [添付ファイル **セーフ]** ページを開き、Microsoft 365 Defenderポータルで開きます<https://security.microsoft.com/safeattachmentv2>。

2. [添付 **ファイルセーフ] ページ** で、[グローバル設定] をクリックし、表示されるフライアウトで次の設定を構成します。
   - **[オンDefender for Office 365、SharePoint、OneDrive、** Microsoft Teams: この設定を有効にする (![[オンに切り替え])。](../../media/scc-toggle-on.png)

     > [!IMPORTANT]
     > **[添付ファイル] セーフ SharePoint、** OneDrive、Microsoft Teamsを有効にする前に、監査ログが組織で有効になっていることを確認してください。 このアクションは、通常、監査ログ ロールが割り当てられているユーザーが実行Exchange Online。 詳細については、「監査ログ検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。

   - **[クライアントセーフドキュメントをOfficeする**: この設定をオンにします (![トグルオン)。](../../media/scc-toggle-on.png) この機能は、必要な種類のライセンスでのみ利用できます。 詳細については、「ドキュメントのセーフ[」を参照Microsoft 365 E5](safe-docs.md)。
   - **[ドキュメント] でファイル** が悪意のあるとセーフした場合でも、保護されたビューをクリックできます。この設定がオフになっていることを確認します (![トグルオフ)。](../../media/scc-toggle-off.png)

   完了したら、[保存] を **クリックします。**

3. [添付ファイル] ページ **セーフ、[** 作成] アイコンを![クリックします](../../media/m365-cc-sc-create-icon.png)。

4. 開く **[添付ファイルセーフ作成**] ポリシー ウィザードで、次の設定を構成します。
   - **ポリシー ページに名前を付** け:
     - **名前**: 一意でわかりやすいものを入力します。
     - **説明**: オプションの説明を入力します。
   - **[ユーザーとドメイン**] ページ: これは最初のポリシーであり、カバレッジを最大化する必要がある可能性が高いので、[ドメイン [](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)] ボックスに受け入れドメインを入力する **必要** があります。 それ以外の場合は、[ **ユーザー** とグループ] **ボックスを使用** して、より詳細な制御を行います。 [これらのユーザー、グループ、ドメインを除外する] を選択し、値を入力することで **、例外を** 指定できます。
   - **設定** ページ:
     - **セーフ添付ファイルの不明なマルウェアの応答**: [ブロック] を **選択します**。
     - **検疫ポリシー**: 既定値は空白で、AdminOnlyAccessPolicy ポリシーが使用されます。 検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作と、ユーザーが検疫通知を受け取るかどうかを定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。
     - **検出された添付ファイルを含む添付ファイル** を **リダイレクトする:** リダイレクトを有効にする: この設定をオン (選択) し、検出されたメッセージを受信する電子メール アドレスを入力します。
     - **スキャンが完了セーフ (** タイムアウトまたはエラー) の場合は、[添付ファイルの検出] 応答を適用します。この設定が選択されているのを確認します。

5. 完了したら、[送信] をクリック **し**、[完了] を **クリックします**。

6. (推奨)グローバル管理者または SharePoint Online 管理者として、**[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを実行し、_DisallowInfectedFileDownload_ `$true` パラメーターを SharePoint Online PowerShell で設定します。
   - `$true` 検出されたファイルのすべてのアクション (削除を除く) をブロックします。 検出されたファイルを開く、移動する、コピーする、共有できない。
   - `$false` 削除とダウンロードを除くすべてのアクションをブロックします。 ユーザーはリスクを受け入れ、検出されたファイルをダウンロードできます。

7. 変更がすべてのデータ センターに広がり、最大 30 Microsoft 365します。

添付ファイル ポリシーと添付ファイルセーフのグローバル設定を構成するセーフ詳細については、次のトピックを参照してください。

- [[添付ファイルセーフポリシーを設定Microsoft Defender for Office 365](set-up-safe-attachments-policies.md)
- [SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする](turn-on-mdo-for-spo-odb-and-teams.md)
- [Microsoft 365 E5 の安全なドキュメント](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>セーフのリンク ポリシー Microsoft Defender for Office 365

リンクの推奨設定の詳細については、「セーフリンクの[セーフ参照してください](recommended-settings-for-eop-and-office365.md#safe-links-settings)。

1. [リンク] **セーフポータル** で [リンク] ページMicrosoft 365 Defender開きます<https://security.microsoft.com/safelinksv2>。

2. [リンク **セーフ] ページで**、[グローバル設定] をクリックし、表示されるフライアウトで次の設定を構成します。
   - **設定アプリセクションのコンテンツに適用されるOffice 365を指定** します。
     - **[セーフアプリOffice 365** リンクを使用する: この設定がオンになっていることを確認します (![トグルオン)。](../../media/scc-toggle-on.png)
     - **ユーザーがアプリで保護された** リンクをクリックOffice 365追跡しない: この設定をオフにします (![トグルオフ)。](../../media/scc-toggle-off.png)
     - **ユーザーがアプリの元の URL** をクリックOffice 365許可しない: この設定がオンになっていることを確認します (![トグルオン)。](../../media/scc-toggle-on.png)

   完了したら、[保存] を **クリックします。**

3. [リンク] ページセーフ **、[** 作成] アイコンを![クリックします](../../media/m365-cc-sc-create-icon.png)。

4. 開く **[リンクセーフ作成**] ポリシー ウィザードで、次の設定を構成します。
   - **ポリシー ページに名前を付** け:
     - **名前**: 一意でわかりやすいものを入力します。
     - **説明**: オプションの説明を入力します。
   - **[ユーザーとドメイン**] ページ: これは最初のポリシーであり、カバレッジを最大化する必要がある可能性が高いので、[ドメイン [](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)] ボックスに受け入れドメインを入力する **必要** があります。 それ以外の場合は、[ **ユーザー** とグループ] **ボックスを使用** して、より詳細な制御を行います。 [これらのユーザー、グループ、ドメインを除外する] を選択し、値を入力することで **、例外を** 指定できます。
   - **Url &保護設定ページをクリック** します。
     - **[メール] セクション内の潜在的に悪意のある URL に対する** アクション:
       - **On: セーフ リンクは、** ユーザーがメール内のリンクをクリックすると、既知の悪意のあるリンクの一覧をチェックします。設定を選択します (オンにします)。
       - **[セーフ組織内で送信された電子メール** メッセージへのリンクを適用する: この設定を選択します (有効にする)。
       - **ファイルを指す疑わしいリンク** やリンクに対してリアルタイムの URL スキャンを適用する: この設定を選択します (オンにします)。
       - **メッセージを配信する前に URL** のスキャンが完了するのを待ちます。この設定を選択します (オンにします)。
       - **URL を書き換えないで**、リンク API セーフを使用してチェックを行います。この設定が選択されていない (オフにする) ことを確認します。
     - **メールで次の URL を書き換え** ない: この設定に関する具体的な推奨事項はありません。 詳細については、「リンク ポリシー」の「次の URL を書き換えない[セーフ参照してください](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)。
     - **[ユーザー] セクションの潜在的に悪意のある URL のMicrosoft Teams** します。
       - ***On: セーフ リンクは**、ユーザーが [リンク] のリンクをクリックすると、既知の悪意のあるリンクの一覧をMicrosoft Teams: この設定を選択します (オンにします)。
     - **[保護設定] セクションを** クリックします。
       - **ユーザークリックの追跡**: この設定が選択 (オン) になっていることを確認します。
       - **ユーザーが元の URL をクリックします**。この設定をオフにします (選択されません)。
       - **通知** ページと警告ページに組織のブランド化を表示する: この設定を選択する (有効にする) のは、「組織の [Microsoft 365](../../admin/setup/customize-your-organization-theme.md) テーマをカスタマイズして会社のロゴをアップロードする」の手順に従った場合にのみ意味があります。
   - **通知** ページ:
     - **ユーザーに通知する方法** セクション: 必要に応じて、[カスタム通知 **テキストを使用** する] を選択して、カスタマイズした通知テキストを入力して使用できます。 カスタム通知テキストを **ユーザーのMicrosoft 翻訳ツール言語** に翻訳するには、[自動ローカライズに使用する] を選択します。 それ以外の場合は、[ **既定の通知テキストを使用する] を** 選択のままにします。

5. 完了したら、[送信] をクリック **し**、[完了] を **クリックします**。

リンク ポリシーとグローバル設定を セーフリンクの構成セーフ詳細については、次のトピックを参照してください。

- [[リンク] セーフポリシーを設定Microsoft Defender for Office 365](set-up-safe-links-policies.md)
- [[リンク] のグローバルセーフ構成Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md)

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a>[オンライン] または [オンライン] または [ファイル] で検出されたSharePointを設定OneDrive for Business

SharePoint Online または OneDrive for Business のファイルが悪意のあるファイルとして識別された場合に通知を受け取る場合は、このセクションの説明に従ってアラートを設定できます。

1. [ポリシー] Microsoft 365 Defenderで<https://security.microsoft.com>、[メール] グループ &**ポリシー**\>&**に** \> **移動します**。

2. [アラート ポリシー **] ページで** 、[新しいアラート **ポリシー] をクリックします**。

3. 新 **しいアラート ポリシー ウィザードが** 開きます。 [名前 **] ページ** で、次の設定を構成します。
   - **名前**: 一意でわかりやすい名前を入力します。 たとえば、「ライブラリ」に「悪意のあるファイル」と入力できます。
   - **説明**: オプションの説明を入力します。
   - **重大度: [** 低] **、[中]**、または **[高]** を **選択します**。
   - **カテゴリ**: [脅威の **管理] を選択します**。

   完了したら、[次へ] を **クリックします。**

4. [アラート設定 **の作成] ページ** で、次の設定を構成します。
   - **何を通知しますか?** セクション: **アクティビティはファイル** \> **内のマルウェアを検出しました**。
   - **[警告をトリガーする方法** ] セクション: [アクティビティがルールに一致する度に確認する **] が** 選択されています。

   完了したら、[次へ] を **クリックします。**

5. [受信者 **の設定] ページで** 、次の設定を構成します。
   - **電子メール通知の送信**: この設定が選択されているのを確認します。
   - **電子メール受信者**: 悪意のあるファイルが検出された場合に通知を受け取る必要がある 1 つ以上のグローバル管理者、セキュリティ管理者、またはセキュリティ リーダーを選択します。
   - **1 日の通知の** 制限: **[制限なし] が** 選択されているを確認します。

   完了したら、[次へ] を **クリックします。**

6. [設定 **の確認] ページ** で、設定を確認し、[ **はい]** を確認し、[オンにする] が選択されている場合は [完了] をクリック **します。**

アラート ポリシーの詳細については、「アラート ポリシー」を参照[Microsoft 365 コンプライアンス センター](../../compliance/alert-policies.md)。

> [!NOTE]
> 構成が完了したら、次のリンクを使用してワークロード調査を開始します。
>
> - [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)
> - [Microsoft 365 Defenderポータルを使用して、検疫済みファイルを管理Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
> - [悪意のあるファイルがオンライン、オンライン、SharePoint、またはOneDriveにMicrosoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
> - [検疫済みメッセージとファイルを管理者として管理Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a>セットアップ後のタスクと次の手順

脅威保護機能を構成したら、それらの機能の動作を監視してください。 必要な操作を行うポリシーを確認して修正します。 また、価値を追加できる新機能やサービス更新プログラムを監視します。

|操作|追加情報|
|---|---|
|レポートを表示して、組織の脅威保護機能がどのように機能しているのか確認する|[電子メール セキュリティ レポート](view-email-security-reports.md) <p> [レポートのMicrosoft Defender for Office 365](view-reports-for-mdo.md) <p> [脅威エクスプローラー](threat-explorer.md)|
|必要に応じて、脅威保護ポリシーを定期的に確認および修正する|[セキュリティ スコア](../defender/microsoft-secure-score.md) <p> [Microsoft 365の調査と対応の機能](./office-365-ti.md)|
|新機能とサービス更新プログラムを監視する|[標準リリースオプションとターゲット リリース オプション](../../admin/manage/release-options-in-office-365.md) <p> [Message Center](../../admin/manage/message-center.md) <p> [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [サービスの説明](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
