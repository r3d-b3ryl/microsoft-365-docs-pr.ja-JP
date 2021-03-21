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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 管理者は、検出されたファイルのアラートを設定する方法など、SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルを有効にする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 300cb3e004010e8ff22de7393d3f3e039bf8cfdd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921146"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft Defender for Office 365 for SharePoint、OneDrive、および Microsoft Teams は、悪意のあるファイルを誤って共有する組織を保護します。 詳細については [、「SharePoint、OneDrive、Microsoft Teams](atp-for-spo-odb-and-teams.md)の安全な添付ファイル」を参照してください。

この記事では、SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルを有効および構成するための手順について説明します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com> でセキュリティ/コンプライアンス センターを開きます。 ATP の [安全な添付ファイル] ページ **に直接移動するには** 、 を開きます <https://protection.office.com/safeattachmentv2> 。

- SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルを有効にするには、セキュリティ& コンプライアンスセンターの組織の管理またはセキュリティ管理者の役割グループのメンバーである必要があります。 詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

- SharePoint Online PowerShell を使用して悪意のあるファイルをダウンロードするユーザーを防ぐには[](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator)、Azure AD のグローバル管理者または[SharePoint 管理者](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator)の役割のメンバーである必要があります。

- 組織で監査ログが有効になっているか確認します。 詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。

- 設定を有効にするには、最大 30 分かかります。

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>手順 1: セキュリティ & コンプライアンス センターを使用して、SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルを有効にする

1. セキュリティ コンプライアンス センターで&管理ポリシー  ATP の安全な添付ファイルに移動し、[ \>  \> グローバル設定]**をクリックします**。

2. 表示される **[グローバル設定** ] フライアウトで **、[SharePoint、OneDrive、および Microsoft Teams** の Office 365 の Defender を有効にする] に移動します。 トグルを右に移動し、[トグル オン] を ![ ](../../media/scc-toggle-on.png) オンにし、SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルを有効にします。

   完了したら、**[保存]** をクリックします。

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Exchange Online PowerShell を使用して SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルを有効にする

PowerShell を使用して SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルを有効にする場合は [、Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) に接続し、次のコマンドを実行します。

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

構文とパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照してください](/powershell/module/exchange/set-atppolicyforo365)。

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>手順 2: (推奨) SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードすることを防止する

既定では、ユーザーは ATP によって検出された悪意のあるファイルを開く、移動、コピー、または共有できます。 ただし、悪意のあるファイルを削除してダウンロードできます。

ユーザーが悪意のあるファイルをダウンロードできない場合は [、SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) に接続し、次のコマンドを実行します。

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**注**:

- この設定は、ユーザーと管理者の両方に影響します。
- ユーザーは引き続き悪意のあるファイルを削除できます。

構文とパラメーターの詳細については [、「Set-SPOTenant」を参照してください](/powershell/module/sharepoint-online/Set-SPOTenant)。

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>手順 3 (推奨) コンプライアンス センターでセキュリティ &を使用して、検出されたファイルのアラート ポリシーを作成する

SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルが悪意のあるファイルを検出したときに、自分と他の管理者に通知するアラート ポリシーを作成できます。 アラートの詳細については、「セキュリティ コンプライアンス センターでアクティビティアラートを作成する [&する」を参照してください](../../compliance/create-activity-alerts.md)。

1. セキュリティ コンプライアンス [センターで&アラート](https://protection.office.com)ポリシーに移動するか \> **、** 開きます <https://protection.office.com/alertpolicies> 。

2. [アラート ポリシー **] ページで、[** 新しいアラート ポリシー **] をクリックします**。

3. 新 **しいアラート ポリシー ウィザード** がフライアウトで開きます。[アラートに **名前を付け] ページ** で、次の設定を構成します。

   - **名前**: 一意でわかりやすい名前を入力します。 たとえば、ライブラリ内の悪意のあるファイル。
   - **説明**: オプションの説明を入力します。 たとえば、SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが検出された場合に管理者に通知します。
   - **重大度 :** 既定値 [低]**を選択** のままにするか、[中] または [高]**を****選択します**。
   - **カテゴリを選択する**: [脅威の **管理] を選択します**。

   完了したら、**[次へ]** をクリックします。

4. [アラート設定 **の作成] ページ** で、次の設定を構成します。

   - **何を通知しますか?:** アクティビティは: ファイル内の **検出されたマルウェアを選択します**。
   - **アラートをトリガーする方法:** アクティビティが選択したルールと一致する度に既定値 **のままに** します。

   完了したら、**[次へ]** をクリックします。

5. [受信者 **の設定] ページで** 、次の設定を構成します。

   - **電子メール通知の送信**: この設定が選択されているのを確認します。 [ **電子メールの受信者]** ボックスで、悪意のあるファイルが検出された場合に通知を受け取る必要がある 1 つ以上のグローバル管理者、セキュリティ管理者、またはセキュリティ リーダーを選択します。
   - **1 日の通知** の制限 : 既定値 [制限 **なし] を** 選択のままにします。

   完了したら、**[次へ]** をクリックします。

6. [設定 **の確認] ページで** 設定を確認し、任意のセクションで [編集] をクリックして変更を加えます。

   [ポリシー **をすぐ有効** にしますか? ] セクションで、既定値 **は [は** い] のままにし、右クリックしてオンにしてください。

   完了したら、 **[完了]** をクリックします。

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>セキュリティ ポリシー&コンプライアンス PowerShell を使用して、検出されたファイルのアラート ポリシーを作成する

前のセクションで説明したように、PowerShell を使用して同じアラート ポリシーを作成する場合は、セキュリティ & コンプライアンス センター [PowerShell](/powershell/exchange/connect-to-scc-powershell) に接続し、次のコマンドを実行します。

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**注**: 既定の _重大度の値は_ 低です。 中または高を指定するには、コマンドに _Severity_ パラメーターと値を含める必要があります。

構文とパラメーターの詳細については [、「New-ActivityAlert」を参照してください](/powershell/module/exchange/new-activityalert)。

### <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

- SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルが正常に有効になっていることを確認するには、次のいずれかの手順を使用します。

  - セキュリティ [](https://protection.office.com)& コンプライアンス センターで、[脅威管理ポリシー  ATP の安全な添付ファイル] に移動し、[グローバル設定] を選択し \>  \> **、[SharePoint、OneDrive、Microsoft Teams の Office 365** の Defender を有効にする] 設定の値を確認します。

  - Exchange Online PowerShell で、次のコマンドを実行してプロパティ設定を確認します。

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    構文とパラメーターの詳細については [、「Get-AtpPolicyForO365」を参照してください](/powershell/module/exchange/get-atppolicyforo365)。

- 悪意のあるファイルのダウンロードが正常にブロックされたことを確認するには、SharePoint Online PowerShell を開き、次のコマンドを実行してプロパティ値を確認します。

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  構文とパラメーターの詳細については [、「Get-SPOTenant」を参照してください](/powershell/module/sharepoint-online/Set-SPOTenant)。

- 検出されたファイルのアラート ポリシーが正常に構成されたことを確認するには、次の手順を実行します。

  - セキュリティ コンプライアンス センターで、[&アラート ポリシー]に移動し、アラート ポリシーを選択し、 \>  \> 設定を確認します。

  - [セキュリティ & コンプライアンス センター PowerShell] で、アラート ポリシーの名前に置き換え、次のコマンドを実行し、プロパティの値 \<AlertPolicyName\> を確認します。

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    構文とパラメーターの詳細については [、「Get-ActivityAlert」を参照してください](/powershell/module/exchange/get-activityalert)。

- [SharePoint、OneDrive、](view-email-security-reports.md#threat-protection-status-report)および Microsoft Teams で検出されたファイルに関する情報を表示するには、脅威保護状態レポートを使用します。 具体的には、[データの表示方法: コンテンツ マルウェア **] ビュー \> を使用** できます。