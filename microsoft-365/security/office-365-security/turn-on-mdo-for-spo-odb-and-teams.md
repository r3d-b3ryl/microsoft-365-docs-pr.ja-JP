---
title: SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 管理者は、検出されたファイルのアラートを設定する方法など、SharePoint、OneDrive、Microsoft Teamsのセーフ添付ファイルを有効にする方法について説明します。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 55923b13cf47e0309a7246ba43dcb9adaf3c58ff
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66016012"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

SharePoint、OneDrive、Microsoft TeamsのMicrosoft Defender for Office 365は、悪意のあるファイルを誤って共有しないように組織を保護します。 詳細については、「[SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル](mdo-for-spo-odb-and-teams.md)」を参照してください。

この記事では、SharePoint、OneDrive、Microsoft Teamsのセーフ添付ファイルを有効にして構成する手順について説明します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[安全な添付ファイル]** ページに直接移動するには、<https://security.microsoft.com/safeattachmentv2> を使用します。

- SharePoint、OneDrive、Microsoft Teamsのセーフ添付ファイルを有効にするには、Microsoft 365 Defender ポータルで **組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。 詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。

- SharePoint Online PowerShell を使用して悪意のあるファイルをユーザーがダウンロードできないようにするには、Azure AD の[グローバル管理者](/azure/active-directory/roles/permissions-reference#global-administrator)ロールまたは [SharePoint管理者](/azure/active-directory/roles/permissions-reference#sharepoint-administrator)ロールのメンバーである必要があります。

- 組織で監査ログが有効になっていることを確認します。 詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。

- 設定を有効にするには、最大 30 分かかります。

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>手順 1: Microsoft 365 Defender ポータルを使用して、SharePoint、OneDrive、Microsoft Teamsのセーフ添付ファイルを有効にする

1. Microsoft 365 Defender ポータルの [ポリシー **] セクションの** <https://security.microsoft.com>[**ポリシー&ルール** \> **脅威ポリシー** \> **セーフ添付ファイル**] に移動します。 **[安全な添付ファイル]** ページに直接移動するには、<https://security.microsoft.com/safeattachmentv2> を使用します。

2. **[安全な添付ファイル]** ページで **[グローバル設定]** をクリックします。

3. 表示される **[グローバル設定**] ポップアップで、[**SharePoint、OneDrive、およびMicrosoft Teamsのファイルの保護**] セクションに移動します。

   **SharePoint、OneDrive、およびMicrosoft Teamsのターン オン Defender for Office 365** を右![トグル オンに移動します。](../../media/scc-toggle-on.png) をクリックして、SharePoint、OneDrive、Microsoft Teamsのセーフ添付ファイルを有効にします。

   完了したら、**[保存]** をクリックします。

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>PowerShell Exchange Online使用して、SharePoint、OneDrive、Microsoft Teamsのセーフ添付ファイルを有効にする

PowerShell を使用してSharePoint、OneDrive、Microsoft Teamsの添付ファイルセーフ有効にする場合は、[powerShell Exchange Online接続](/powershell/exchange/connect-to-exchange-online-powershell)し、次のコマンドを実行します。

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

構文とパラメーターの詳細については、「 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)」を参照してください。

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>手順 2: (推奨) SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードできないようにする

既定では、ユーザーは、SharePoint、OneDrive、およびMicrosoft Teamsのセーフ添付ファイルによって検出された悪意のあるファイルを開いたり、移動したり、コピーしたり、共有<sup>\*</sup>したりすることはできません。 ただし、悪意のあるファイルを削除してダウンロードできます。

<sup>\*</sup> ユーザーが **[アクセスの管理]** に移動しても、[ **共有** ] オプションは引き続き使用できます。

ユーザーが悪意のあるファイルをダウンロードできないようにするには、[SharePoint Online PowerShell に接続](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)し、次のコマンドを実行します。

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**注意**:

- この設定は、ユーザーと管理者の両方に影響します。
- ユーザーは引き続き悪意のあるファイルを削除できます。

構文とパラメーターの詳細については、「 [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)」を参照してください。

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a>手順 3 (推奨) Microsoft 365 Defender ポータルを使用して、検出されたファイルのアラート ポリシーを作成する

SharePoint、OneDrive、およびMicrosoft Teamsの添付ファイルをセーフして悪意のあるファイルを検出したときに、自分や他の管理者に通知するアラート ポリシーを作成できます。 アラートの詳細については、「 [アラート ポリシー」を](../../compliance/alert-policies.md)参照してください。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール** \> **アラート ポリシー**] に移動します。 **[通知ポリシー]** ページに直接移動するには、<https://security.microsoft.com/alertpolicies> を使用します。

2. [ **アラート ポリシー** ] ページで、[ **新しいアラート ポリシー**] をクリックします。

3. **新しいアラート ポリシー** ウィザードがポップアップで開きます。[**アラートの名前]** ページで、次の設定を構成します。
   - **名前**: 一意でわかりやすい名前を入力します。 たとえば、ライブラリ内の悪意のあるファイルなどです。
   - **説明**: 省略可能な説明を入力します。 たとえば、SharePoint Online、OneDrive、またはMicrosoft Teamsで悪意のあるファイルが検出されたときに管理者に通知します。
   - **重大度**: ドロップダウン リストから **[低****]、[中]**、または **[高]** を選択します。
   - **カテゴリ**: ドロップダウン リストから **[脅威管理** ] を選択します。

   完了したら、**[次へ]** をクリックします。

4. [ **アラート設定の作成]** ページで、次の設定を構成します。
   - アラートの対象 **は何ですか?** セクション \> **アクティビティは、**\>ドロップダウン リストから **ファイル内の検出されたマルウェア** を選択します。
   - **アラートをトリガーする方法** セクション: アクティビティが選択した **ルールと一致するたびに既定値のままに** します。

   完了したら、**[次へ]** をクリックします。

5. [ **受信者の設定] ページで** 、次の設定を構成します。
   - **[電子メール通知の送信]** が選択されていることを確認します。 [ **電子メール受信者** ] ボックスで、悪意のあるファイルが検出されたときに通知を受け取る必要がある 1 人以上のグローバル管理者、セキュリティ管理者、またはセキュリティ 閲覧者を選択します。
   - **日次通知の制限**: 既定値は [ **制限なし]** を選択したままにします。

   完了したら、**[次へ]** をクリックします。

6. [ **設定の確認]** ページで、設定を確認します。 各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

   [ **ポリシーをすぐに有効にしますか?** ] セクションで、既定値は **[はい] のままにし、すぐにオンにします** 。

   完了したら、 **[完了]** をクリックします。

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>セキュリティ & コンプライアンス PowerShell を使用して、検出されたファイルのアラート ポリシーを作成する

PowerShell を使用して前のセクションで説明したのと同じアラート ポリシーを作成する場合は、 [Security & Compliance PowerShell に接続](/powershell/exchange/connect-to-scc-powershell) し、次のコマンドを実行します。

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**注**: 既定の _重大度_ の値は [低] です。 中または高を指定するには、コマンドに _重大度_ パラメーターと値を含めます。

構文とパラメーターの詳細については、「 [New-ActivityAlert」を](/powershell/module/exchange/new-activityalert)参照してください。

### <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

- SharePoint、OneDrive、Microsoft Teamsのセーフ添付ファイルが正常に有効になっていることを確認するには、次のいずれかの手順を使用します。

  - Microsoft 365 Defender ポータルで、[**ポリシー&ルール** \> **の脅威ポリシー** \> **ポリシー**] セクション **セーフ [添付ファイル] セクション**\>に移動し、[**グローバル設定**] を選択して、[**SharePointのDefender for Office 365を有効にする] の値を確認します。OneDriveとMicrosoft Teams** 設定。

  - Exchange Online PowerShell で、次のコマンドを実行してプロパティ設定を確認します。

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    構文とパラメーターの詳細については、「 [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)」を参照してください。

- 悪意のあるファイルのダウンロードをユーザーが正常にブロックしたことを確認するには、SharePoint Online PowerShell を開き、次のコマンドを実行してプロパティ値を確認します。

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  構文とパラメーターの詳細については、「 [Get-SPOTenant」を](/powershell/module/sharepoint-online/Set-SPOTenant)参照してください。

- 検出されたファイルのアラート ポリシーが正常に構成されたことを確認するには、次のいずれかの手順を使用します。
  - Microsoft 365 Defender ポータルで、**ポリシー &ルール**\>アラート ポリシーに移動して **アラート ポリシー**\>を選択し、設定を確認します。
  - Microsoft 365 Defender ポータルの PowerShell で、アラート ポリシーの名前に置き換え\<AlertPolicyName\>、次のコマンドを実行し、プロパティ値を確認します。

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    構文とパラメーターの詳細については、「 [Get-ActivityAlert」を](/powershell/module/exchange/get-activityalert)参照してください。

- [脅威の保護状態レポート](view-email-security-reports.md#threat-protection-status-report)を使用して、SharePoint、OneDrive、Microsoft Teamsで検出されたファイルに関する情報を表示します。 具体的には、[ **データの表示方法: コンテンツ \> マルウェア** ] ビューを使用できます。
