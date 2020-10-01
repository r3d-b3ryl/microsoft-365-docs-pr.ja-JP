---
title: Office 365 の ATP-SharePoint、OneDrive、& Teams をオンにする
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 検出されたファイルに対して通知を設定する方法など、SharePoint、OneDrive、Teams の ATP を有効にする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1cd345ae74b81c23f92b9e9b7d712efa8b875503
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326903"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Office 365 Advanced Threat Protection (ATP) for SharePoint、OneDrive、Microsoft Teams は、悪意のあるファイルを誤って共有することから組織を保護します。 詳細については、「 [SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)」を参照してください。

この記事には、SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にして構成するための手順が含まれています。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com> でセキュリティ/コンプライアンス センターを開きます。 [ATP の安全な **添付ファイル** ] ページに直接移動するには、を開き <https://protection.office.com/safeattachmentv2> ます。

- SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にするには、セキュリティ & コンプライアンスセンターの [ **組織の管理** ] または [ **セキュリティ管理者** ] の役割グループのメンバーである必要があります。 詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

- SharePoint Online の PowerShell を使用して、悪意のあるファイルがダウンロードされないようにするには、Azure AD の [全体管理者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) または [sharepoint 管理者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) ロールのメンバーである必要があります。

- 組織の監査ログが有効になっていることを確認します。 詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。

- 設定が有効になるまで最大30分間待ちます。

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>手順 1: セキュリティ & コンプライアンスセンターを使用して、SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動し、[ **グローバル設定**] をクリックします。

2. [ **グローバル設定** ] が表示されたら、 **[SharePoint、OneDrive、MICROSOFT Teams の ATP を有効** にする] 設定に移動します。 右にトグルをオンにして、 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にします。

   完了したら、**[保存]** をクリックします。

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Exchange Online の PowerShell を使用して、SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする

PowerShell を使用して、SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする場合は、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) して次のコマンドを実行します。

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

構文およびパラメーターの詳細については、「 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)」を参照してください。

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>手順 2: (推奨) SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードできないようにする

既定では、ユーザーは ATP によって検出された悪意のあるファイルを開く、移動、コピー、または共有することはできません。 ただし、悪意のあるファイルを削除してダウンロードすることはできます。

ユーザーが悪意のあるファイルをダウンロードできないようにするには、 [SharePoint Online PowerShell に接続](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) し、次のコマンドを実行します。

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**注**:

- この設定は、ユーザーと管理者の両方に影響します。
- ユーザーは悪意のあるファイルを削除できます。

構文およびパラメーターの詳細については、「 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)」を参照してください。

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>手順 3 (推奨) セキュリティ & コンプライアンスセンターを使用して、検出されたファイルの通知ポリシーを作成する

SharePoint、OneDrive、Microsoft Teams 用の ATP が悪意のあるファイルを検出したときに通知する通知ポリシーを作成できます。 通知の詳細については、「 [セキュリティ & コンプライアンスセンターでアクティビティ警告を作成](../../compliance/create-activity-alerts.md)する」を参照してください。

1. [ [セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[ **alerts** \> **Alert policies** ] または [open] に移動し <https://protection.office.com/alertpolicies> ます。

2. [ **通知ポリシー** ] ページで、[ **新しいアラートポリシー**] をクリックします。

3. **新しい通知ポリシー**ウィザードがフライアウトで開きます。[**通知の名前**を指定してください] ページで、次の設定を構成します。

   - [**名前**]: わかりやすい一意の名前を入力します。 たとえば、ライブラリ内の悪意のあるファイル。
   - **説明**: 省略可能な説明を入力します。 たとえば、SharePoint Online、OneDrive、Microsoft Teams で悪意のあるファイルが検出されたときに管理者に通知します。
   - **重要度**: 既定値の [ **低** ] を選択したままにするか、[ **中** ] または [ **高**] を選択します。
   - **カテゴリを選択**します。 [ **脅威管理**] を選択します。

   完了したら、**[次へ]** をクリックします。

4. [ **通知設定の作成** ] ページで、次の設定を構成します。

   - 通知対象を選択してください。**アクティビティは**次のとおりです。 [**ファイルに検出されたマルウェア**] を選択します。
   - **通知をどのようにトリガーしますか?**: アクティビティが選択した **ルールと一致** するたびに、既定値をそのまま使用します。

   完了したら、**[次へ]** をクリックします。

5. [ **受信者の設定** ] ページで、次の設定を構成します。

   - **電子メール通知の送信**: この設定が選択されていることを確認します。 [ **電子メールの宛先** ] ボックスで、悪意のあるファイルが検出されたときに通知を受信する必要がある1人以上のグローバル管理者、セキュリティ管理者、またはセキュリティ閲覧者を選択します。
   - [**毎日の通知制限数**: 既定値のままにします。 (**制限なし**)。

   完了したら、**[次へ]** をクリックします。

6. [ **設定の確認** ] ページで設定を確認し、いずれかのセクションの [ **編集** ] をクリックして変更を加えます。

   [ポリシーをすぐ **に有効** にしますか?] セクションで、既定値の **[はい] を** 選択し、[すぐにオン] を選択します。

   完了したら、 **[完了]** をクリックします。

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>セキュリティ & コンプライアンス PowerShell を使用して、検出されたファイルの通知ポリシーを作成する

PowerShell を使用して、前のセクションで説明したのと同じアラートポリシーを作成する場合は、「 [Security & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) し、次のコマンドを実行します。

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**注**: 既定の _重要度_ の値は低くなっています。 中または高を指定するには、コマンドに _Severity_ パラメーターと値を含めます。

構文およびパラメーターの詳細については、「 [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)」を参照してください。

### <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

- SharePoint、OneDrive、Microsoft Teams の ATP が正常に有効化されたことを確認するには、次のいずれかの手順を使用します。

  - [セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[脅威の**管理** \> **ポリシー]** \> ATP の [安全な**添付ファイル**] に移動し、[**グローバル設定**] を選択して、 **[SharePoint、OneDrive、および Microsoft Teams の**設定] の設定値を確認します。

  - Exchange Online PowerShell で次のコマンドを実行して、プロパティの設定を確認します。

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    構文およびパラメーターの詳細については、「 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)」を参照してください。

- ユーザーが悪意のあるファイルをダウンロードできないようにしたことを確認するには、SharePoint Online PowerShell を開き、次のコマンドを実行してプロパティの値を確認します。

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  構文およびパラメーターの詳細については、「 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)」を参照してください。

- 検出されたファイルのアラートポリシーが正常に構成されたことを確認するには、次のいずれかの手順を使用します。

  - セキュリティ & コンプライアンスセンターで、[アラートの**アラート**ポリシー] に移動して \> **Alert policies** \> 通知ポリシーを選択し、設定を確認します。

  - セキュリティ & コンプライアンスセンターの PowerShell で、を \<AlertPolicyName\> アラートポリシーの名前に置き換え、次のコマンドを実行して、プロパティの値を確認します。

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    構文およびパラメーターの詳細については、「 [取得-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)」を参照してください。

- [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)を使用して、SharePoint、OneDrive、Microsoft Teams の検出されたファイルに関する情報を表示します。 具体的には、[ **データの表示方法: コンテンツ \> マルウェア** ] ビューを使用できます。
