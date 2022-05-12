---
title: ドメインに参加している Windows 10 デバイスをビジネス向けの Microsoft 365 で管理できるようにする
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
description: Microsoft 365 がローカル Active Directory に参加している Windows 10 デバイスを保護する方法について説明します。
ms.openlocfilehash: de50fc8ac5ad3fe5d5f8cd5cfdfd781d94062358
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65319096"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>ドメインに参加している Windows 10 デバイスを Microsoft 365 Business Premium で管理できるようにする

組織でオンプレミスの Windows Server Active Directory を使用している場合は、ローカル認証を必要とするオンプレミス リソースへのアクセスを維持しながら、Windows 10 デバイスを保護する Microsoft 365 Business Premium を設定できます。

この保護を設定するのに、**Hybrid Azure AD に参加しているデバイス** を実装できます。 これらのデバイスは、オンプレミスの Active Directory と Azure Active Directory の両方に参加しています。

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日以降、Microsoft 365 Business Premium のお客様に展開されます。 このオファリングでは、デバイスに追加のセキュリティ機能が提供されます。 [Defender for Business の詳細については、こちらをご覧ください](../security/defender-business/mdb-overview.md)。

## <a name="watch-configure-hybrid-azure-active-directory-join"></a>視聴する: Hybrid Azure Active Directory 参加を構成する

このビデオでは、最も一般的なシナリオに対してこれを設定する方法の手順について説明します。これについては、次の手順でも詳しく説明します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a>開始する前に

- Azure AD Connect を使用してユーザーを Azure AD に同期します。
- 組織単位 (OU) 同期 Azure AD Connect 完了します。
- 同期するすべてのドメイン ユーザーに、Microsoft 365 Business Premium へのライセンスがあることを確認します。

手順については、「[ドメイン ユーザーを Microsoft 365 に同期する](../admin/setup/manage-domain-users.md)」を参照してください。

## <a name="1-verify-mdm-authority-in-intune"></a>1. Intuneで MDM 機関を確認する

Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)) に移動し、[**デバイス登録**] を選択し、[**概要**] ページで **MDM 機関** が **Intune** になっていることを確認します。

- **MDM 機関** が **None の** 場合は、**MDM 機関** をクリックして **Intune** に設定します。
- **MDM 機関** が **Microsoft Office 365** になっている場合は、[**デバイス**]  >  [**デバイスの登録**] に移動し、右側の [**MDM 機関の追加**] ダイアログを使用して [**Intune MDM**] 機関を追加します ([**MDM 機関の追加**] ダイアログは、**MDM 機関** が [Microsoft Office 365] に設定されている場合にのみ使用できます)。

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. コンピューターに参加するために Azure ADが有効になっていることを確認する

1. Microsoft 365 管理センターに <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>移動し、**管理センター** の一覧 **で Azure Active Directory** ( Azure Active Directory が表示されていない場合は [すべて表示] を選択) を選択します。 

2. **Azure Active Directory 管理センター** で、**Azure Active Directory** に移動し、[**デバイス**] を選択し、[**デバイスの設定]** を選択します。

3. **ユーザーがデバイスに参加して Azure AD が有効になっている** ことを確認する 

    1. すべてのユーザーを有効にするには、[**すべて**] に設定します。

    2. 特定のユーザーを有効にするには、[**選択済み**] に設定して、特定のユーザー グループを有効にします。

        - Azure AD で同期された目的のドメイン ユーザーを [[セキュリティ グループ](../admin/create-groups/create-groups.md)] に追加します。

        - [**グループの選択**] を選択して、そのセキュリティ グループの MDM ユーザー スコープを有効にします。

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Azure AD が MDM に対して有効になっていることを確認する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> で Microsoft 365 管理センターに移動し、**[エンドポイント管理]** を選択します (**エンドポイント マネージャー** が表示されない場合は、[**すべて表示**] を選択します)

2. **Microsoft エンドポイント マネージャー管理センター** で、[**デバイス**]  >  [**Windows**]  >  [**Windows 登録**]  >  [**自動登録**] に移動します。

3. MDM ユーザー スコープが有効になっていることを確認します。

    1. すべてのコンピューターを登録するには、[**すべて**] に設定すると、ユーザーが Windows に仕事用アカウントを追加したときに、Azure AD に参加しているすべてのユーザー コンピューターと新しいコンピューターが自動的に登録されます。
  
    2. 特定のユーザー グループのコンピューターを登録するには、[**一部**] に設定します。
  
        -  Azure AD で同期された目的のドメイン ユーザーを [[セキュリティ グループ](/admin/create-groups/create-groups.md)] に追加します。
  
       -  [**グループの選択**] を選択して、そのセキュリティ グループの MDM ユーザー スコープを有効にします。

## <a name="4-create-the-required-resources"></a>4. 必要なリソースを作成する 

[ハイブリッド Azure AD 結合を構成](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)するために必要なタスクを実行する作業は、[SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell モジュールで見つかった [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) コマンドレットを使用することで簡略化されました。 このコマンドレットを呼び出すと、必要なサービス接続ポイントとグループ ポリシーが作成され、構成されます。

このモジュールをインストールするには、PowerShell のインスタンスから次を呼び出します。

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Azure AD Connect を実行している Windows サーバーにこのモジュールをインストールします。

必要なサービス接続ポイントとグループ ポリシーを作成するには、[Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) コマンドレットを呼び出します。 このタスクを実行するときは、Microsoft 365 Business Premium グローバル管理者資格情報が必要です。 リソースを作成する準備ができたら、次を呼び出します。

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

最初のコマンドは Microsoft クラウドとの接続を確立し、メッセージが表示されたら、Microsoft 365 Business Premium グローバル管理者資格情報を指定します。

## <a name="5-link-the-group-policy"></a>5. グループ ポリシーをリンクする

1. グループ ポリシー管理コンソール (GPMC) で、ポリシーをリンクする場所を右クリックし、コンテキスト メニューから [*既存の GPO のリンク*] を選択します。

2. 上記の手順で作成したポリシーを選択し、[**OK**] をクリックします。

## <a name="get-the-latest-administrative-templates"></a>最新の管理用テンプレート ツールをダウンロードします。

**既定の Azure AD 資格情報を使用して MDM の自動登録を有効にする** ポリシーが表示されない場合は、Windows 10 バージョン 1803 以降用の ADMX がインストールされていない可能性があります。この問題を解決するには、次の手順に従います (注: 最新の MDM.admx は下位互換性があります)。

1. [Windows 10 October 2020 更新プログラム (20H2) 用の管理用テンプレート (.admx)](https://www.microsoft.com/download/102157) をダウンロードしてインストールします。

2. ドメイン コントローラーにパッケージをインストールします。

3. 管理用テンプレートのバージョンに応じて、フォルダーに移動します: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**。

4. 上記のパスの **Policy Definition** フォルダーの名前を **PolicyDefinitions** に変更します。

5. 既定では、**PolicyDefinitions** フォルダーを既定では `C:\Windows\SYSVOL\domain\Policies` にある SYSVOL 共有にコピーします。

   ドメイン全体に対して中央ポリシー ストアを使用する予定がある場合は、そこに PolicyDefinitions の内容を追加します。

6. 複数のドメイン コントローラーがある場合は、ポリシーが使用できるよう SYSVOL がレプリケートされるまで待ちます。 この手順は、今後のバージョンの管理用テンプレートでも利用できます。

この時点で、**使用可能な既定の Azure AD 資格情報を使用して MDM の自動登録を有効にするポリシー** を確認できます。

## <a name="related-content"></a>関連コンテンツ

- [ドメイン ユーザーを Microsoft 365 に同期する](../admin/setup/manage-domain-users.md)

- [Exchange 管理センターで役割グループを作成する](../admin/create-groups/create-groups.md)

- [チュートリアル: マネージド ドメインの Hybrid Azure Active Directory 参加を構成する](/azure/active-directory/devices/hybrid-azuread-join-managed-domains)

- [セルフサービス パスワードを設定する](../admin/add-users/let-users-reset-passwords.md)

- [セルフサービスによるグループ管理をセットアップする](/azure/active-directory/enterprise-users/groups-self-service-management)

- [ビジネス プランの Microsoft 365 をセキュリティで保護するためのベスト プラクティス](../admin/security-and-compliance/secure-your-business-data.md)

## <a name="next-objective"></a>次の目標

[Office クライアントの展開の準備](m365bp-prepare-for-office-client-deployment.md)