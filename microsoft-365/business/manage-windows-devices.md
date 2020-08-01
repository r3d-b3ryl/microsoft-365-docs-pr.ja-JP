---
title: Microsoft 365 for business で管理されるドメインに参加している Windows 10 デバイスを有効にする
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: いくつかの手順で、Microsoft 365 を有効にして、ローカルの Active Directory に参加している Windows 10 デバイスを保護する方法について説明します。
ms.openlocfilehash: 2eaf5aa76cae1680b93af008af615ae872e4fb20
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533787"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Microsoft 365 Business Premium によって管理されるドメインに参加している Windows 10 デバイスを有効にする

組織でオンプレミスの Windows Server Active Directory を使用している場合は、Microsoft 365 Business Premium をセットアップして Windows 10 デバイスを保護することができます。ただし、ローカル認証を必要とするオンプレミスのリソースへのアクセスは維持されます。
この保護をセットアップするには、**ハイブリッド AZURE AD に参加**しているデバイスを実装します。 これらのデバイスは、オンプレミスの Active Directory と Azure Active Directory の両方に参加します。

このビデオでは、最も一般的なシナリオに対してこれを設定する手順について説明します。これについては、以下の手順でも詳細に説明します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>作業を開始する前に、以下の手順を完了していることを確認してください。
- Azure AD Connect を使用してユーザーを Azure AD に同期します。
- 完全な Azure AD Connect 組織単位 (OU) 同期。
- 同期するすべてのドメインユーザーが Microsoft 365 Business Premium のライセンスを持っていることを確認してください。

手順については、「[ドメインユーザーを Microsoft に同期させる](manage-domain-users.md)」を参照してください。

## <a name="1-verify-mdm-authority-in-intune"></a>1. Intune で MDM 機関を確認する

Portal.azure.com に移動し、Intune のページ検索の上部に移動します。
[Microsoft Intune] ページで、[**デバイスの登録**] を選択し、[**概要**] ページで**MDM authority**が**Intune**であることを確認します。

- **Mdm 機関**が**なし**の場合は、 **mdm 機関**をクリックして**Intune**に設定します。
- **MDM 機関**が**Microsoft office 365**の場合は、[**デバイス**を  >  **登録**する] を選択し、 **Intune mdm**機関を追加する権限の [ **mdm 機関の追加**] ダイアログを使用します (mdm 機関を追加するに**は、mdm**機関が microsoft Office 365 に設定**され**ている場合にのみ使用できます)。

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Azure AD が参加しているコンピューターに対して有効になっていることを確認する

- 管理センターに移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> して、[**管理**センター] の一覧にある [azure **active** directory が表示されていない場合はすべて表示] を選択します。 
- **Azure Active directory 管理センター**で、[ **azure active directory** ] に移動し、[**デバイス**]、[**デバイスの設定**] の順に選択します。
- **ユーザーがデバイスを AZURE AD に参加させる**ことが可能であることを確認する 
    1. すべてのユーザーを有効にするには、 **all**に設定します。
    2. 特定のユーザーを有効にするには、[**オン**] に設定して特定のユーザーグループを有効にします。
        - Azure AD で同期されている目的のドメインユーザーを[セキュリティグループ](../admin/create-groups/create-groups.md)に追加します。
        - **[グループの選択**] を選択して、そのセキュリティグループの MDM ユーザースコープを有効にします。

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. MDM に対して Azure AD が有効になっていることを確認する

- 管理センターに移動し、[ <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **エンドポイント Managemen**の選択] を選択します (**エンドポイントマネージャー**が表示されない場合は [**すべて表示**] を選択します)
- **Microsoft エンドポイントマネージャー管理センター**で、[**デバイス**  >  **windows**  >  **windows 登録**の  >  **自動登録**] に移動します。
- MDM ユーザースコープが有効になっていることを確認します。

    1. すべてのコンピューターを登録するには、[**すべて**] に設定して、ユーザーが Windows に作業アカウントを追加するときに、Azure AD と新しいコンピューターに参加するすべてのユーザーコンピューターを自動的に登録します。
    2. 特定のユーザーグループのコンピューターを登録するには、[**一部**] に設定します。
        -  Azure AD で同期されている目的のドメインユーザーを[セキュリティグループ](../admin/create-groups/create-groups.md)に追加します。
        -  **[グループの選択**] を選択して、そのセキュリティグループの MDM ユーザースコープを有効にします。

## <a name="4-create-the-required-resources"></a>4. 必要なリソースを作成する 

[ハイブリッド AZURE AD join の構成](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)に必要なタスクを実行することは、 [secmgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell モジュールにある[SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)コマンドレットを使用することによって簡略化されました。 このコマンドレットを呼び出すと、必要なサービス接続ポイントとグループポリシーが作成および構成されます。

このモジュールは、PowerShell のインスタンスから次を呼び出してインストールできます。

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> このモジュールは、Azure AD Connect を実行している Windows サーバーにインストールすることをお勧めします。

必要なサービス接続ポイントとグループポリシーを作成するには、 [SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)コマンドレットを呼び出します。 このタスクを実行するときには、Microsoft 365 Business Premium グローバル管理者の資格情報が必要になります。 リソースを作成する準備ができたら、次のように呼び出します。

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

最初のコマンドは、Microsoft クラウドとの接続を確立し、メッセージが表示されたら、Microsoft 365 Business Premium グローバル管理者の資格情報を指定します。

## <a name="5-link-the-group-policy"></a>5. グループポリシーをリンクする

1. グループポリシー管理コンソール (GPMC) で、ポリシーをリンクする場所を右クリックし、コンテキストメニューから [既存の*GPO のリンク*] を選択します。
2. 上記の手順で作成したポリシーを選択し、[ **OK]** をクリックします。

## <a name="get-the-latest-administrative-templates"></a>最新の管理用テンプレートを取得する

**既定の AZURE AD 資格情報を使用した自動 MDM 登録を有効に**するポリシーが表示されない場合は、Windows 10、バージョン1803、バージョン1809、またはバージョン1903用の ADMX がインストールされていない可能性があります。 この問題を解決するには、次の手順を実行します (注: 最新の MDM は下位互換性があります)。

1.  ダウンロード: [Windows 10 の管理用テンプレート (admx) は2019更新プログラム (1903) の場合があり](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all)ます。
2.  プライマリドメインコントローラー (PDC) にパッケージをインストールします。
3.  フォルダーのバージョンに応じて、次の操作を行います。 **C:\Program files (x86) \Microsoft Group Policy\Windows 10 5 月 2019 Update (1903) v3**。
4.  上記のパスの**ポリシー定義**フォルダーの名前を**policydefinitions**に変更します。
5.  **Policydefinitions**フォルダーを**C:\Windows\SYSVOL\domain\Policies**にコピーします。 
    -   ドメイン全体に対して中央ポリシーストアを使用することを計画している場合は、そこに PolicyDefinitions の内容を追加します。
6.  ポリシーを使用可能にするには、プライマリドメインコントローラーを再起動します。 この手順は、将来のバージョンでも同様に機能します。

この時点で、[**既定の AZURE AD 資格情報を使用して MDM の自動登録を有効に**する] ポリシーが表示されます。
