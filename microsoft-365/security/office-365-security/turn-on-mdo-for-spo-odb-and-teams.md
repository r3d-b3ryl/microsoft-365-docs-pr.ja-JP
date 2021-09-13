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
description: 管理者は、セーフ SharePoint、OneDrive、Microsoft Teams、Microsoft Teams の添付ファイルを有効にする方法について説明します。検出されたファイルのアラートを設定する方法も含まれます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8a1020193a49dd7b4871b9b9fec53d21073b03e6
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211554"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender for Office 365、SharePoint、OneDrive、Microsoft Teamsファイルを誤って共有する組織を保護します。 詳細については、「[SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル](mdo-for-spo-odb-and-teams.md)」を参照してください。

この記事では、添付ファイルの有効化と構成セーフ、SharePoint、OneDrive、およびMicrosoft Teams。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 [添付ファイル] ページに直接 **移動セーフ開** きます <https://security.microsoft.com/safeattachmentv2> 。

- SharePoint、OneDrive、および Microsoft Teams の添付ファイルを有効にするには、Microsoft 365 Defender ポータルの組織の管理またはセキュリティ管理者の役割グループのメンバーである必要があります。セーフ 詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。

- SharePoint Online PowerShell を使用して悪意のあるファイルをダウンロードするユーザーを防ぐには、Azure [](/azure/active-directory/roles/permissions-reference#global-administrator) AD のグローバル管理者または[SharePoint 管理者](/azure/active-directory/roles/permissions-reference#sharepoint-administrator)の役割のメンバーである必要があります。

- 組織で監査ログが有効になっているか確認します。 詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。

- 設定を有効にするには、最大 30 分かかります。

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>手順 1: Microsoft 365 Defender ポータルを使用して、セーフ SharePoint、OneDrive、およびMicrosoft Teams

1. ポータルで、[Microsoft 365 Defenderのルールの脅威ポリシーポリシー  ] セクション&に移動し、[添付 \>  \>  \> **セーフします**。

2. [添付ファイル **セーフ] ページで**、[グローバル設定]**をクリックします**。

3. 表示される **[グローバル設定**] フライアウトで、[ファイルの保護] セクションSharePoint、OneDrive、Microsoft Teamsします。 

   [Defender を **有効にする] Office 365、SharePoint、OneDrive、Microsoft Teams** トグルを右のトグル オンに ![ 移動します。](../../media/scc-toggle-on.png) をクリックして、セーフ、SharePoint、OneDrive、およびMicrosoft Teams。

   完了したら、**[保存]** をクリックします。

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>PowerShell Exchange Onlineを使用して、セーフ、SharePoint、OneDriveの添付ファイルMicrosoft Teams

SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルを有効にする場合は[、Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続し、次のコマンドを実行します。

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

構文とパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照してください](/powershell/module/exchange/set-atppolicyforo365)。

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>手順 2: (推奨) オンライン PowerShell SharePointを使用して、ユーザーが悪意のあるファイルをダウンロードすることを防止する

既定では、SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルによって検出された悪意のあるファイルを開く、移動、コピー、または共有 <sup>\*</sup> Microsoft Teams。 ただし、悪意のあるファイルを削除してダウンロードできます。

<sup>\*</sup> ユーザーが [アクセスの管理 **] に移動** した場合でも、[ **共有** ] オプションは引き続き使用できます。

ユーザーが悪意のあるファイルをダウンロードできない場合は、オンライン[powerShell SharePointに](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)接続し、次のコマンドを実行します。

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**注**:

- この設定は、ユーザーと管理者の両方に影響します。
- ユーザーは引き続き悪意のあるファイルを削除できます。

構文とパラメーターの詳細については [、「Set-SPOTenant」を参照してください](/powershell/module/sharepoint-online/Set-SPOTenant)。

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a>手順 3 (推奨) Microsoft 365 Defenderを使用して、検出されたファイルのアラート ポリシーを作成する

SharePoint、OneDrive、および Microsoft Teams の添付ファイルが悪意のあるファイルを検出したときに、セーフ 管理者に通知するアラート ポリシーを作成できます。 アラートの詳細については、「アラート ポリシー [」を参照してください](../../compliance/alert-policies.md)。

1. [ポリシー] Microsoft 365 Defenderに移動し、[ポリシー] **&** \> **ポリシーを** 開きます <https://security.microsoft.com/alertpolicies> 。

2. [アラート ポリシー **] ページで** 、[新しいアラート ポリシー **] をクリックします**。

3. 新 **しいアラート ポリシー ウィザード** がフライアウトで開きます。[アラートに **名前を付け] ページ** で、次の設定を構成します。
   - **名前**: 一意でわかりやすい名前を入力します。 たとえば、ライブラリ内の悪意のあるファイル。
   - **説明**: オプションの説明を入力します。 たとえば、悪意のあるファイルがオンライン、SharePoint、またはOneDriveで検出Microsoft Teams。
   - **重大度 :** ドロップダウン リストから **[低****]、[中**]、または [高] を選択します。
   - **カテゴリ**: ドロップダウン **リストから [脅威** の管理] を選択します。

   完了したら、**[次へ]** をクリックします。

4. [アラート設定 **の作成] ページ** で、次の設定を構成します。
   - **何を通知しますか?** section \> **Activity is** \> Select **Detected malware in file from** the drop down list.
   - **アラートをトリガーする** 方法セクション: 既定値のままにする **アクティビティが選択したルールと一致する度** に指定します。

   完了したら、**[次へ]** をクリックします。

5. [受信者 **の設定] ページで** 、次の設定を構成します。
   - [電子 **メール通知の送信] が** 選択されているのを確認します。 [ **電子メールの受信者]** ボックスで、悪意のあるファイルが検出された場合に通知を受け取る必要がある 1 つ以上のグローバル管理者、セキュリティ管理者、またはセキュリティ リーダーを選択します。
   - **1 日の通知** の制限 : 既定値 [制限 **なし] を** 選択のままにします。

   完了したら、**[次へ]** をクリックします。

6. [設定 **の確認] ページで** 、設定を確認します。 各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

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

- SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルが正常に有効になっていることを確認するには、次のいずれかの手順を実行します。

  - Microsoft 365 Defender ポータルで、[ポリシー & **rules** Threat \>  \> **Policies Policies]** セクション \> **セーフ Attachments** に移動し、[グローバル設定] を選択し、[SharePoint、OneDrive、および Microsoft Teams の Office 365 の Defender を有効にする] 設定の値を確認します。

  - PowerShell Exchange Onlineで、次のコマンドを実行してプロパティ設定を確認します。

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
  - [ポリシー] Microsoft 365 Defenderに移動し、[ポリシー  ] &アラート ポリシーを選択し、 \>  \> 設定を確認します。
  - ポータル powerShell Microsoft 365 Defenderで、アラート ポリシーの名前に置き換え、次のコマンドを実行し、プロパティ \<AlertPolicyName\> 値を確認します。

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    構文とパラメーターの詳細については [、「Get-ActivityAlert」を参照してください](/powershell/module/exchange/get-activityalert)。

- 脅威保護[の状態レポートを使用](view-email-security-reports.md#threat-protection-status-report)して、検出されたファイルに関する情報を、SharePoint、OneDrive、およびMicrosoft Teams。 具体的には、[データの表示方法: コンテンツ マルウェア **] ビュー \> を使用** できます。
