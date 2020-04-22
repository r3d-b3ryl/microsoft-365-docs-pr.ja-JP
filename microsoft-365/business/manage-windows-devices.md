---
title: Microsoft 365 for business で管理されるドメインに参加している Windows 10 デバイスを有効にする
f1.keywords:
- NOCSH
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
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: いくつかの手順で、Microsoft 365 を有効にして、ローカルの Active Directory に参加している Windows 10 デバイスを保護する方法について説明します。
ms.openlocfilehash: 431c1be74723e156befb13ffe1ed98b48b9a23cb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633285"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-for-business"></a>Microsoft 365 for business で管理されるドメインに参加している Windows 10 デバイスを有効にする

組織がオンプレミスの Windows Server Active Directory を使用している場合は、ローカル認証を必要とするオンプレミスのリソースへのアクセスを維持しながら、Microsoft 365 for business をセットアップして、Windows 10 デバイスを保護することができます。
この保護をセットアップするには、**ハイブリッド AZURE AD に参加**しているデバイスを実装します。 これらのデバイスは、オンプレミスの Active Directory と Azure Active Directory の両方に参加します。

このビデオでは、最も一般的なシナリオに対してこれを設定する手順について説明します。これについては、以下の手順でも詳細に説明します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. ディレクトリ同期の準備 

ローカル Active Directory ドメインからユーザーとコンピューターを同期する前に、「 [Office 365 へのディレクトリ同期の準備](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization)」を参照してください。 特に次のようになります。

   - 次の属性について、ディレクトリに重複が存在しないことを確認してください。 **mail**、 **ProxyAddresses**、および**userPrincipalName**。 これらの値は一意である必要があり、重複して削除する必要があります。
   
   - 各ローカルユーザーアカウントの**userPrincipalName** (UPN) 属性を、ライセンスされた Microsoft 365 ユーザーに対応するプライマリ電子メールアドレスと一致するように構成することをお勧めします。 例: mary.shelley@contoso.com ではなく*mary@contoso* 、 *mary.shelley@contoso.com*
   
   - Active Directory ドメインが、 *.com*または *.org*などのインターネットでルーティング可能なサフィックスの代わりに、*ローカル*ユーザーアカウントの UPN サフィックスではなく、ルーティング可能*ではない*サフィックスで終わっている場合は、「[ディレクトリ同期のために非ルーティングドメインを準備する](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)」で説明されているように、まずローカルユーザーアカウントの UPN サフィックスを調整します。 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Azure AD Connect をインストールして構成します。

ユーザー、グループ、および連絡先をローカルの Active directory から Azure Active Directory に同期するには、Azure Active Directory Connect をインストールし、ディレクトリ同期をセットアップします。 詳細については、「 [Office 365 のディレクトリ同期をセットアップ](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)する」を参照してください。

> [!NOTE]
> この手順は、Microsoft 365 for business の場合とまったく同じです。 

Azure AD Connect のオプションを構成する際には、**パスワード同期**、**シームレスなシングルサインオン**、**パスワード書き戻し**機能を有効にすることをお勧めします。これは、Microsoft 365 for business でもサポートされています。

> [!NOTE]
> Azure AD Connect のチェックボックスを超えてパスワードを書き戻しするには、いくつかの追加の手順があります。 詳細については、「[方法: パスワードの書き戻しを構成](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)する」を参照してください。 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. ハイブリッド Azure AD Join を構成する

ハイブリッド Azure AD に参加するように Windows 10 デバイスを有効にする前に、次の前提条件を満たしていることを確認してください。

   - Azure AD Connect の最新バージョンを実行していること。

   - Azure AD connect は、ハイブリッド Azure AD に参加させるデバイスのすべてのコンピューターオブジェクトを同期しています。 コンピューターオブジェクトが特定の組織単位 (OU) に属している場合は、それらの Ou が Azure AD connect の同期にも設定されていることを確認してください。

ハイブリッド Azure AD に参加している既存のドメインに参加している Windows 10 デバイスを登録するには、[チュートリアル「管理ドメインのハイブリッド Azure Active Directory の参加を構成](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)する」の手順を実行します。 このハイブリッドにより、既存のオンプレミスの Active Directory が Windows 10 台のコンピューターに参加し、クラウドを準備できるようになります。
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. Windows 10 の自動登録を有効にする

 Intune でモバイルデバイス管理用に Windows 10 デバイスを自動的に登録するには、「[グループポリシーを使用して windows 10 デバイスを自動的に登録](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)する」を参照してください。 グループポリシーをローカルコンピューターレベルで設定することも、一括操作の場合は、グループポリシー管理コンソールおよび ADMX テンプレートを使用して、ドメインコントローラーにこのグループポリシー設定を作成することもできます。

## <a name="5-configure-seamless-single-sign-on"></a>5. シームレスなシングルサインオンを構成する

  シームレスな SSO は、企業のコンピューターを使用している場合に、ユーザーの Microsoft 365 クラウドリソースに自動的に署名します。 「 [Azure Active Directory シームレスシングルサインオン: クイックスタート](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature)」に記載されている2つのグループポリシーオプションのいずれかを展開するだけです。 [**グループポリシー] オプション**では、ユーザーが設定を変更することはできませんが、**グループポリシーの優先順位**オプションで値が設定されていて、ユーザーが構成可能なままになります。

## <a name="6-set-up-windows-hello-for-business"></a>6. Windows Hello for Business のセットアップ

 Windows Hello for Business では、ローカルコンピューターにサインインするための強力な2要素認証 (2FA) を使用してパスワードを置き換えています。 1つの要素は非対称キーの組で、もう1つの要素は、デバイスでサポートされている場合は、指紋または顔認識などの PIN またはその他のローカルジェスチャです。 可能な場合は、パスワードを2FA および Windows Hello for Business に置き換えることをお勧めします。

ハイブリッド Windows Hello for Business を構成するには、「[ハイブリッドキー信頼 Windows hello For business の前提条件](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs)」を確認してください。 その後、「 [Configure Hybrid Windows Hello For Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings)」の手順に従います。 
