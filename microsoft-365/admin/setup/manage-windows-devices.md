---
title: ドメインに参加しているデバイスWindows 10、ビジネス向けドメインにMicrosoft 365有効にする
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: ローカルの Active-Directory に参加Microsoft 365デバイスを保護するために、Windows 10をわずか数ステップで有効にする方法について説明します。
ms.openlocfilehash: 28c9b9da1bc830c2a17e531b398a34b50949ba54
ms.sourcegitcommit: 24bff8a546491ff32ebf04d1f51abb3197035706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59786234"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>ドメインに参加しているデバイスWindows 10デバイスをユーザーが管理Microsoft 365 Business Premium

組織で Windows Server Active Directory オンプレミスを使用している場合は、Microsoft 365 Business Premium をセットアップして Windows 10 デバイスを保護しながら、ローカル認証を必要とするオンプレミス リソースへのアクセスを維持できます。
この保護を設定するには、参加しているデバイスに **ハイブリッド Azure AD実装できます**。 これらのデバイスは、オンプレミスの Active Directory とユーザーの両方に参加Azure Active Directory。

## <a name="watch-configure-hybrid-azure-active-directory-join"></a>ウォッチ: ハイブリッド サーバーへの参加Azure Active Directory構成する

このビデオでは、最も一般的なシナリオでこれを設定する手順について説明します。この手順については、以下の手順でも説明します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a>開始する前に

- ユーザーを Azure AD Azure AD Connect。
- 組織単位 (OU) AD Connect Azure 組織単位 (OU) の同期を完了します。
- 同期するドメイン ユーザー全員にライセンスが割り当てMicrosoft 365 Business Premium。

手順については [、「ドメイン ユーザーを Microsoft に同期する](manage-domain-users.md) 」を参照してください。

## <a name="1-verify-mdm-authority-in-intune"></a>1. Intune で MDM 機関を確認する

[管理者][エンドポイント マネージャー](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)に移動し、[デバイスMicrosoft Intune登録]を選択し、[概要]ページで **、MDM 機関** が Intune である必要 **があります**。

- **MDM 機関が** **None の場合は****、MDM 機関** をクリックして Intune に **設定します**。
- **MDM 機関** がMicrosoft Office 365 の場合は、[デバイス登録デバイス] に移動し、右側の [MDM 機関の追加] ダイアログを使用して Intune MDM 機関を追加します (MDM 機関の追加ダイアログは  >  **、MDM Authority** が Microsoft Office 365 に設定されている場合にのみ使用できます)。

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Azure AD参加が有効になっているか確認する

- [管理センター] に移動し、[管理センター] Azure Active Directoryで [すべて表示する] ([Azure Active Directoryを表示 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> する]**を選択** します。  
- 管理センターで **、[Azure Active Directory]** に移動し、[デバイス]  **Azure Active Directory[** デバイスの設定] の順 **に選択します**。
- ユーザー **がデバイスを Azure に参加する可能性AD** 確認する 
    1. すべてのユーザーを有効にするには、[すべて] に **設定します**。
    2. 特定のユーザーを有効にするには、[選択] **に** 設定して、特定のユーザー グループを有効にします。
        - Azure で同期された目的のドメイン ユーザーをセキュリティ ADに [追加します](../../admin/create-groups/create-groups.md)。
        - [グループ **の選択]** を選択して、そのセキュリティ グループの MDM ユーザー スコープを有効にします。

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. MDM で Azure ADが有効になっているか確認する

- 管理センターに移動し、[エンドポイント管理] t を選択します ([表示しない場合エンドポイント マネージャー <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> を表示する] を選択します)   
- 管理センター **Microsoft エンドポイント マネージャー、[** 登録自動登録 **] の**[デバイス] Windows Windows  >    >    >  **に移動します**。
- MDM ユーザー スコープが有効になっているか確認します。

    1. すべてのコンピューターを登録するには、[すべて] に設定して、ユーザーが作業用アカウントを Windows に追加するときに、Azure AD に参加しているすべてのユーザー コンピューターと新しいコンピューターを自動的に登録します。
    2. 特定の **ユーザー グループ** のコンピューターを登録するには、[一部] に設定します。
        -  Azure で同期された目的のドメイン ユーザーをセキュリティ ADに [追加します](../create-groups/create-groups.md)。
        -  [グループ **の選択]** を選択して、そのセキュリティ グループの MDM ユーザー スコープを有効にします。

## <a name="4-create-the-required-resources"></a>4. 必要なリソースを作成する 

ハイブリッド[Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)参加を構成するために必要なタスクを実行すると[、SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell モジュールにある[Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)コマンドレットを使用して簡略化されました。 このコマンドレットを呼び出すと、必要なサービス接続ポイントとグループ ポリシーが作成および構成されます。

このモジュールは、PowerShell のインスタンスから次のコマンドを呼び出してインストールできます。

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> このモジュールは、Azure サーバーを実行しているサーバー WindowsインストールAD Connect。

必要なサービス接続ポイントとグループ ポリシーを作成するには  [、Initialize-SecMgmtHybirdDeviceEnrollment コマンドレットを呼び出](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) します。 このタスクを実行するMicrosoft 365 Business Premium管理者資格情報を使用する必要があります。 リソースを作成する準備ができたら、次のコマンドを呼び出します。

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

最初のコマンドは、Microsoft クラウドとの接続を確立し、メッセージが表示されたら、グローバル管理者資格情報Microsoft 365 Business Premium指定します。

## <a name="5-link-the-group-policy"></a>5. グループ ポリシーのリンク

1. グループ ポリシー管理コンソール (GPMC) で、ポリシーをリンクする場所を右クリックし、コンテキスト メニューから [既存 *の GPO...* をリンクする] を選択します。
2. 上記の手順で作成したポリシーを選択し **、[OK] をクリックします**。

## <a name="get-the-latest-administrative-templates"></a>最新の管理用テンプレートを取得する

[既定の Azure AD 資格情報を使用して **自動 MDM** 登録を有効にする] ポリシーが表示されない場合は、Windows 10 バージョン 1803 以降の ADMX がインストールされていない可能性があります。 問題を解決するには、次の手順に従います (注: 最新の MDM.admx は下位互換性があります)。

1. ダウンロード: [2020 年 10 月更新プログラム (20H2)](https://www.microsoft.com/download/102157)Windows 10管理用テンプレート (.admx) をダウンロードします。
2. ドメイン コントローラーにパッケージをインストールします。
3. 管理用テンプレートのバージョンに応じて、フォルダーに移動します **。C:\Program Files (x86)\Microsoft グループ ポリシー\Windows 10 2020 年 10 月更新 (20H2)**。
4. 上記の **パスの [ポリシー定義]** フォルダーの名前を **PolicyDefinitions に変更します**。
5. **PolicyDefinitions** フォルダーを既定で **C:\Windows\SYSVOL\domain\Policyes** にある SYSVOL 共有にコピーします。
   - ドメイン全体で中央ポリシー ストアを使用する場合は、PolicyDefinitions のコンテンツをそこに追加します。
6. 複数のドメイン コントローラーがある場合は、ポリシーが使用可能になるまで SYSVOL がレプリケートされるのを待ちます。 この手順は、将来のバージョンの管理用テンプレートでも機能します。

この時点で、既定の Azure アカウント資格情報を使用して **自動 MDM** 登録を有効にするポリシー AD確認できます。

## <a name="related-content"></a>関連コンテンツ

[ドメイン ユーザーを他のユーザー Microsoft 365](manage-domain-users.md)同期する (記事)\
[管理センターでグループを作成](../create-groups/create-groups.md) する (記事)\
[チュートリアル: 管理ドメインAzure Active Directoryハイブリッド ドメインへの参加を構成する](/azure/active-directory/devices/hybrid-azuread-join-managed-domains)(記事)