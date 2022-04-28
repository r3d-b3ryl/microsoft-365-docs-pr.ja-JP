---
title: オンプレミス環境とのMicrosoft 365統合
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: この記事では、Microsoft 365を既存のディレクトリ サービスやオンプレミス環境と統合する方法について説明します。
ms.openlocfilehash: a3ba75fd2f2b69e71d5b14b14e17827ed96e4dd4
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093901"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>オンプレミス環境とのMicrosoft 365統合

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365を既存の オンプレミスの Active Directory Domain Services (AD DS) と統合し、Exchange Server、Skype for Business Server 2015、または SharePoint Server のオンプレミス インストールと統合できます。
  
 - AD DS を統合すると、両方の環境のユーザー アカウントを同期および管理できます。 ユーザーがオンプレミスの資格情報を使用して両方の環境にログオンできるように、パスワード ハッシュ同期 (PHS) またはシングル サインオン (SSO) を追加することもできます。
 - オンプレミスサーバー製品と統合すると、ハイブリッド環境が作成されます。 ハイブリッド環境は、ユーザーや情報をMicrosoft 365に移行する際に役立つ場合もあれば、一部のユーザーまたは一部の情報をオンプレミスとクラウドに引き続き含めることができます。 ハイブリッド環境の詳細については、 [ハイブリッド クラウド](../solutions/cloud-architecture-models.md#hybrid)に関するページを参照してください。

Microsoft 365 管理センターのカスタマイズされたセットアップ ガイダンスには、Azure Active Directory (Azure AD) アドバイザーを使用することもできます (Microsoft 365にサインインする必要があります)。

- [Azure ADセットアップ ガイド](https://aka.ms/aadpguidance)
- [組織のディレクトリからユーザーを同期する](https://aka.ms/aadconnectpwsync)
- [Active Directory フェデレーション サービス (AD FS) (AD FS) デプロイ アドバイザー](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>開始する前に

Microsoft 365とオンプレミス環境を統合する前に、[ネットワーク計画とパフォーマンスチューニング](network-planning-and-performance.md)も行う必要があります。 また、使用可能な [ID モデル](deploy-identity-solution-identity-model.md)についても理解する必要があります。 

[Microsoft 365 ユーザー アカウントの管理](manage-microsoft-365-accounts.md)に使用できるツールの一覧については、Microsoft 365 アカウントの管理に関するページを参照してください。 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>MICROSOFT 365と AD DS を統合する

AD DS に既存のユーザー アカウントがある場合は、これらのアカウントをすべてMicrosoft 365に再作成する必要がなく、環境間に違いやエラーが発生するリスクがあります。 ディレクトリ同期は、オンプレミス環境とオンライン環境の間でこれらのアカウントをミラーリングするのに役立ちます。 ディレクトリ同期を使用すると、ユーザーは環境ごとに新しい情報を覚える必要がなく、アカウントを 2 回作成または更新する必要はありません。 ディレクトリ同期のために [オンプレミス ディレクトリを準備する](prepare-for-directory-synchronization.md) 必要があります。
  
![ディレクトリ同期を使用して、オンプレミスとオンラインのユーザー アカウント情報を同期します。](../media/microsoft-365-integration/directory-synchronization.png)
  
ユーザーがオンプレミスの資格情報を使用してMicrosoft 365にログオンできるようにするには、SSO を構成することもできます。 SSO を使用すると、ユーザー認証のためにオンプレミス環境を信頼するようにMicrosoft 365が構成されます。
  
![シングル サインオンでは、オンプレミス環境とオンライン環境の両方で同じアカウントを使用できます。](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>パスワード ハッシュ同期またはパススルー認証 (PTA) の有無にかかわらずディレクトリ同期

ユーザー は、ユーザー アカウント (domain\username) を使用してオンプレミス環境にログオンします。 Microsoft 365に移動するときは、職場または学校のアカウント (user@domain.com) で再度ログオンする必要があります。 ユーザー名は両方の環境で同じです。 PHS または PTA を追加すると、ユーザーは両方の環境で同じパスワードを持ちますが、Microsoft 365にログオンするときに資格情報をもう一度指定する必要があります。 PHS とのディレクトリ同期は、最も一般的に使用されるディレクトリ同期です。

ディレクトリ同期を設定するには、Azure AD Connectを使用します。 手順については、「高速設定を使用してMicrosoft 365とAzure AD Connect[のディレクトリ同期](set-up-directory-synchronization.md)[を設定する」を参照](/azure/active-directory/hybrid/how-to-connect-install-express)してください。

[Microsoft 365へのディレクトリ同期の準備](prepare-for-directory-synchronization.md)について詳しくは、こちらを参照してください。

### <a name="directory-synchronization-with-sso"></a>SSO を使用したディレクトリ同期

ユーザーは、自分のユーザー アカウントを使用してオンプレミス環境にログオンします。 Microsoft 365に移動すると、自動的にログオンするか、オンプレミス環境で使用するのと同じ資格情報 (domain\username) を使用してログオンします。

SSO を設定するには、Azure AD Connectも使用します。 手順については、「[Azure AD Connectのカスタム インストール](/azure/active-directory/hybrid/how-to-connect-install-custom)」を参照してください。

詳細については、「 [シングル サインオン](/azure/active-directory/manage-apps/what-is-single-sign-on)」を参照してください。

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD Connectでは、DirSync やAzure AD Syncなどの古いバージョンの ID 統合ツールが置き換えられます。Azure Active Directory同期からAzure AD Connectに更新する場合は、[アップグレード手順を](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started)参照してください。 

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)