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
ms.localizationpriority: medium
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
ms.openlocfilehash: b57d9f4f13985d5d67b39d6486df089b82f4f05c
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64635398"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>ドメインに参加しているデバイスWindows 10をユーザーが管理Microsoft 365 Business Premium

> [!NOTE]
> Microsoft Defender for Business 2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 この機能は、デバイスに追加のセキュリティ機能を提供します。 [Defender for Business の詳細については、「Defender for Business」を参照してください](../security/defender-business/mdb-overview.md)。

組織で Windows Server Active Directory オンプレミスを使用している場合は、Microsoft 365 Business Premium をセットアップして Windows 10 デバイスを保護しながら、ローカル認証を必要とするオンプレミス リソースへのアクセスを維持できます。
この保護を設定するには、ハイブリッド デバイスと参加 **Azure AD実装できます**。 これらのデバイスは、ユーザーのデバイスとオンプレミスの Active Directoryの両方にAzure Active Directory。

## <a name="watch-configure-hybrid-azure-active-directory-join"></a>ウォッチ: ハイブリッド サーバーへの参加Azure Active Directory構成する

このビデオでは、最も一般的なシナリオでこれを設定する手順について説明します。この手順については、以下の手順でも説明します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a>開始する前に

- ユーザーをユーザーとAzure AD同期Azure AD Connect。
- 組織Azure AD Connect (OU) の同期を完了します。
- 同期するドメイン ユーザー全員にライセンスが割り当てMicrosoft 365 Business Premium。

手順については[、「ドメイン ユーザーを同期Microsoft 365](../admin/setup/manage-domain-users.md)を参照してください。

## <a name="1-verify-mdm-authority-in-intune"></a>1. サーバーで MDM 機関を確認Intune

管理センター () Microsoft エンドポイント マネージャーに [https://endpoint.microsoft.com](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)移動し、[デバイスの登録] を選択し、[概要]  ページで **MDM 機関** が有効 **Intune。**

- **MDM 機関が** **None の場合** は、**MDM 機関** をクリックして、MDM 機関を [有効] **Intune**。
- **MDM 機関** が **Microsoft Office 365** の場合は、**DevicesEnroll**  >  デバイスに移動し、右側の [MDM 機関の追加] ダイアログを使用して **Intune MDM** 機関を追加します (MDM 機関の追加ダイアログは、**MDM Authority** が Microsoft Office 365 に設定されている場合にのみ使用できます)。

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. コンピューター Azure ADが有効になっているか確認する

1. [管理センター] **Microsoft 365 管理センターに**<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>移動しAzure Active Directory [表示しない場合Azure Active Directoryを表示する] **を選択** します。 

2. 管理センターで **Azure Active Directoryに移動** し、[デバイス] **Azure Active Directory****[デバイス** の設定] **の順に選択します**。

3. **VerifyUsers が有効になっているデバイスに参加Azure AD** 可能性があります 

    1. すべてのユーザーを有効にするには、[すべて] に **設定します**。

    2. 特定のユーザーを有効にするには、[選択] **に** 設定して、特定のユーザー グループを有効にします。

        - グループ内で同期された目的のドメイン ユーザー Azure ADセキュリティ グループに[追加します](../admin/create-groups/create-groups.md)。

        - [グループ **の選択]** を選択して、そのセキュリティ グループの MDM ユーザー スコープを有効にします。

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. MDM Azure ADが有効になっているか確認する

1. [エンドポイントの管理] Microsoft 365 管理センターに <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>移動し、[エンドポイントの管理]  を **選択します (**[すべての **エンドポイント マネージャーを表示** する] を選択します)

2. 管理センター **Microsoft エンドポイント マネージャーに移動****し、[デバイス** >  > Windows **Windows登録** > **] に移動します**。

3. MDM ユーザー スコープが有効になっているか確認します。

    1. すべてのコンピューターを登録するには、[すべて] に設定すると、Azure AD に参加しているすべてのユーザー コンピューターと、ユーザーが作業用アカウントを Windows に追加するときに新しいコンピューターが自動的に登録されます。
  
    2. 特定の **ユーザー グループ** のコンピューターを登録するには、[一部] に設定します。
  
        -  グループ内で同期された目的のドメイン ユーザー Azure ADセキュリティ グループに[追加します](/admin/create-groups/create-groups.md)。
  
       -  [グループ **の選択]** を選択して、そのセキュリティ グループの MDM ユーザー スコープを有効にします。

## <a name="4-create-the-required-resources"></a>4. 必要なリソースを作成する 

ハイブリッド [Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) 参加を構成するために必要なタスクを実行すると、[SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell モジュールにある [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) コマンドレットを使用して簡略化されました。 このコマンドレットを呼び出すと、必要なサービス接続ポイントとグループ ポリシーが作成および構成されます。

このモジュールは、PowerShell のインスタンスから次のコマンドを呼び出してインストールできます。

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> このモジュールは、サーバーを実行WindowsサーバーにインストールAzure AD Connect。

必要なサービス接続ポイントとグループ ポリシーを作成するには、  [Initialize-SecMgmtHybirdDeviceEnrollment コマンドレットを呼び出](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) します。 このタスクを実行するMicrosoft 365 Business Premium管理者資格情報を使用する必要があります。 リソースを作成する準備ができたら、次のコマンドを呼び出します。

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

最初のコマンドは、Microsoft クラウドとの接続を確立し、メッセージが表示されたら、グローバル管理者資格情報Microsoft 365 Business Premium指定します。

## <a name="5-link-the-group-policy"></a>5. [リンク] グループ ポリシー

1. [グループ ポリシー管理コンソール (GPMC) で、ポリシーをリンクする場所を右クリックし、コンテキスト メニューから [既存 *の GPO のリンク]* を選択します。

2. 上記の手順で作成したポリシーを選択し、[OK] を **クリックします**。

## <a name="get-the-latest-administrative-templates"></a>最新の管理用テンプレートを取得する

[既定の Azure AD 資格情報を使用して **自動 MDM** 登録を有効にする] ポリシーが表示されない場合は、Windows 10 バージョン 1803 以降の ADMX がインストールされていない可能性があります。 問題を解決するには、次の手順に従います (注: 最新の MDM.admx は下位互換性があります)。

1. ダウンロード: [2020 年 10 月の更新プログラム (20H2) Windows 10管理用テンプレート (.admx) をダウンロードします](https://www.microsoft.com/download/102157)。

2. ドメイン コントローラーにパッケージをインストールします。

3. 管理用テンプレートのバージョンに応じて、フォルダーに移動します。**C:\Program Files (x86)\Microsoft グループ ポリシー\Windows 10 2020 Update (20H2)**)。

4. 上記の **パスの [ポリシー定義]** フォルダーの名前を **PolicyDefinitions に変更します**。

5. **PolicyDefinitions フォルダー** を SYSVOL 共有に既定でコピーします`C:\Windows\SYSVOL\domain\Policies`。既定では .

   ドメイン全体で中央ポリシー ストアを使用する場合は、PolicyDefinitions のコンテンツをそこに追加します。

6. 複数のドメイン コントローラーがある場合は、ポリシーが使用可能になるまで SYSVOL がレプリケートされるのを待ちます。 この手順は、将来のバージョンの管理用テンプレートでも機能します。

この時点で、既定の資格情報を使用して **自動 MDM** 登録を有効にするポリシーを確認Azure AD必要があります。

## <a name="related-content"></a>関連コンテンツ

- [ドメイン ユーザーを Microsoft 365](../admin/setup/manage-domain-users.md)(article)\ に同期する

- [管理センターでグループを作成](../admin/create-groups/create-groups.md) する (記事)\

- [チュートリアル: 管理ドメインAzure Active Directoryハイブリッド ドメインへの参加を構成する](/azure/active-directory/devices/hybrid-azuread-join-managed-domains) (記事)

- [ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法](../admin/security-and-compliance/secure-your-business-data.md)
