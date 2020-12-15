---
title: Microsoft Defender for Office 365 ( SharePoint、OneDrive、& Teams) を有効にする
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 検出されたファイルのアラートを設定する方法など、SharePoint、OneDrive、Teams の ATP を有効にする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 44d487810156d5de5ae152e08040e8dccd2a4ee0
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682601"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Microsoft Defender for Office 365 for SharePoint、OneDrive、および Microsoft Teams は、悪意のあるファイルを誤って共有する組織を保護します。 詳細については [、SharePoint、OneDrive、Microsoft Teams の ATP に関するページを参照してください](atp-for-spo-odb-and-teams.md)。

この記事では、SharePoint、OneDrive、および Microsoft Teams の ATP を有効にし、構成する手順について説明します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com> でセキュリティ/コンプライアンス センターを開きます。 [ATP の安全な添付ファイル **] ページに直接移動するには** 、開きます <https://protection.office.com/safeattachmentv2> 。

- SharePoint、OneDrive、および Microsoft Teams の ATP を有効にする場合は、セキュリティ/コンプライアンスセンターの組織の管理役割グループまたはセキュリティ管理者役割グループのメンバーである必要&があります。 詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

- SharePoint Online PowerShell を使用してユーザーが悪意のあるファイルをダウンロードするのを防[](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator)ぐには、Azure AD のグローバル管理者または[SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator)管理者ロールのメンバーである必要AD。

- 組織で監査ログが有効になっているか確認します。 詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。

- 設定を有効にできる時間は最大 30 分です。

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>手順 1: セキュリティ/コンプライアンス センター&使用して、SharePoint、OneDrive、および Microsoft Teams の ATP を有効にする

1. セキュリティ/コンプライアンス センター&、**脅威管理** ポリシー ATP の安全な添付ファイルに移動し、[グローバル設定] \>  \> を **クリックします**。

2. 表示される **グローバル設定** のフライアウトで **、SharePoint、OneDrive、Microsoft Teams** の ATP を有効にする設定に移動します。 トグルを右に切り替え ![ ](../../media/scc-toggle-on.png) 、SharePoint、OneDrive、Microsoft Teams の ATP を有効にします。

   完了したら、**[保存]** をクリックします。

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Exchange Online PowerShell を使用して SharePoint、OneDrive、Microsoft Teams の ATP を有効にする

PowerShell を使用して SharePoint、OneDrive、Microsoft Teams の ATP を有効にする場合は [、Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) に接続し、次のコマンドを実行します。

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

構文およびパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)してください。

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>手順 2: (推奨) SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードすることを防ぐ

既定では、ユーザーは ATP によって検出された悪意のあるファイルを開く、移動する、コピーする、共有できない。 ただし、悪意のあるファイルを削除してダウンロードすることができます。

ユーザーが悪意のあるファイルをダウンロードできないのを防ぐには [、SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) に接続し、次のコマンドを実行します。

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**注**:

- この設定は、ユーザーと管理者の両方に影響します。
- 悪意のあるファイルは引き続き削除できます。

構文およびパラメーターの詳細については [、「Set-SPOTenant」を参照してください](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>手順 3 (推奨) セキュリティ センターとコンプライアンス センター&使用して、検出されたファイルのアラート ポリシーを作成する

SharePoint、OneDrive、および Microsoft Teams の ATP が悪意のあるファイルを検出したときに、自分や他の管理者に通知するアラート ポリシーを作成できます。 アラートの詳細については、「セキュリティ/コンプライアンス センターでのアクティビティアラート& [参照してください](../../compliance/create-activity-alerts.md)。

1. セキュリティ/ [コンプライアンス センターで&](https://protection.office.com)アラート **ポリシー** に移動するか \> **、開** きます <https://protection.office.com/alertpolicies> 。

2. [アラート **ポリシー] ページで、[** 新しいアラート **ポリシー] をクリックします**。

3. アラート **ポリシーの新規ウィザード** がフライアウトで開きます。[アラート **に名前を付け] ページで** 、次の設定を構成します。

   - **名前**: 一意でわかりやすい名前を入力します。 たとえば、ライブラリ内の悪意のあるファイル。
   - **説明**: オプションの説明を入力します。 たとえば、SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが検出された場合に管理者に通知します。
   - **重要度 :** 既定値の [低] **を選択** のままにするか、[中] または [高 **]** を選択 **します**。
   - **Select a category**: Select **Threat management**.

   完了したら、**[次へ]** をクリックします。

4. [アラート **設定の作成] ページ** で、次の設定を構成します。

   - **What do you want to alert on?: Activity is:** Select **Detected malware in file**.
   - **アラートをトリガー** する方法: アクティビティが選択したルールと一致する度に既定値 **のままに** します。

   完了したら、**[次へ]** をクリックします。

5. [受信者 **の設定] ページで** 、次の設定を構成します。

   - **電子メール通知の送信**: この設定が選択されているのを確認します。 [ **電子メールの受信者** ] ボックスで、悪意のあるファイルが検出された場合に通知を受け取る必要がある 1 人または複数のグローバル管理者、セキュリティ管理者、またはセキュリティ 閲覧者を選択します。
   - **1 日の通知** 制限 : 既定値 [制限 **なし] を** 選択したままにしてください。

   完了したら、**[次へ]** をクリックします。

6. [設定 **の確認] ページ** で設定を確認し、セクションの [編集] をクリックして変更を行います。

   [ **ポリシーを今すぐ** 有効にしますか? ] セクションで、既定値 **は [は** い] のままにし、そのままオンにしてください。

   完了したら、 **[完了]** をクリックします。

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Security & Compliance PowerShell を使用して、検出されたファイルのアラート ポリシーを作成する

前のセクションで説明したのと同じアラート ポリシーを PowerShell を使用して作成する場合は、セキュリティ & コンプライアンス センター [の PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) に接続し、次のコマンドを実行します。

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**注**: 既定の _重要度の値_ は低です。 中または高を指定するには、コマンドに _Severity_ パラメーターと値を含める必要があります。

構文およびパラメーターの詳細については [、「New-ActivityAlert」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)。

### <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

- SharePoint、OneDrive、Microsoft Teams の ATP が正常に有効になっていることを確認するには、次のいずれかの手順を使用します。

  - セキュリティ &[コンプライアンス](https://protection.office.com)センターで、脅威管理ポリシー  ATP の安全な添付ファイルに移動し、[グローバル設定] を選択して \>  \> **、[Atp for SharePoint、OneDrive、および Microsoft Teams** を有効にする] 設定の値を確認します。

  - Exchange Online PowerShell で、次のコマンドを実行してプロパティの設定を確認します。

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    構文およびパラメーターの詳細については [、Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)を参照してください。

- 悪意のあるファイルのダウンロードが正常にブロックされたことを確認するには、SharePoint Online PowerShell を開き、次のコマンドを実行してプロパティ値を確認します。

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  構文およびパラメーターの詳細については [、「Get-SPOTenant」を参照してください](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。

- 検出されたファイルに対してアラート ポリシーが正常に構成されたことを確認するには、次の手順を使用します。

  - セキュリティ/コンプライアンス センター&アラート アラート ポリシーに移動し、アラート ポリシーを選択し、 \>  \> 設定を確認します。

  - Security & Compliance Center PowerShell で、アラート ポリシーの名前に置き換え、次のコマンドを実行して、プロパティ値 \<AlertPolicyName\> を確認します。

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    構文およびパラメーターの詳細については [、「Get-ActivityAlert」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)。

- 脅威保護 [状態レポートを使用して](view-email-security-reports.md#threat-protection-status-report) 、SharePoint、OneDrive、および Microsoft Teams で検出されたファイルに関する情報を表示します。 具体的には、[データの表示方法: コンテンツ マルウェア] ビュー **\> を使用** できます。
