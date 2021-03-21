---
title: Microsoft 365 とオンプレミス環境との統合
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: この記事では、Microsoft 365 を既存のディレクトリ サービスおよびオンプレミス環境と統合する方法について説明します。
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923968"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Microsoft 365 とオンプレミス環境との統合

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 を既存のオンプレミスの Active Directory ドメイン サービス (AD DS) と、Exchange Server、Skype for Business Server 2015、または SharePoint Server のオンプレミス インストールと統合できます。
  
 - DS を統合AD、両方の環境のユーザー アカウントを同期および管理できます。 また、パスワード ハッシュ同期 (PHS) またはシングル サインオン (SSO) を追加して、ユーザーがオンプレミスの資格情報を使用して両方の環境にログオンすることもできます。
 - オンプレミスのサーバー製品と統合する場合は、ハイブリッド環境を作成します。 ハイブリッド環境は、ユーザーや情報を Microsoft 365 に移行する場合や、一部のユーザーまたは一部の情報をオンプレミスとクラウドに引き続き持つ場合に役立ちます。 ハイブリッド環境の詳細については、「ハイブリッド クラウド」 [を参照してください](../solutions/cloud-architecture-models.md#hybrid)。

Microsoft 365 管理センターでカスタマイズされたセットアップ ガイダンスに Azure Active Directory (Azure AD) アドバイザーを使用できます (Microsoft 365 にサインインする必要があります)。

- [Azure ADセットアップ ガイド](https://aka.ms/aadpguidance)
- [組織のディレクトリからユーザーを同期する](https://aka.ms/aadconnectpwsync)
- [Active Directory フェデレーション サービス (AD FS) 展開アドバイザー](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>はじめに

Microsoft 365 とオンプレミス環境を統合する前に、ネットワーク計画とパフォーマンス [調整も行う必要があります](network-planning-and-performance.md)。 また、使用可能な ID モデルも [理解する必要があります](about-microsoft-365-identity.md)。 

Microsoft [365](manage-microsoft-365-accounts.md) ユーザー アカウントの管理に使用できるツールの一覧については、「Microsoft 365 アカウントの管理」を参照してください。 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>Microsoft 365 を DS と統合ADする

AD DS に既存のユーザー アカウントがある場合は、Microsoft 365 のすべてのアカウントを作成し、環境間に違いやエラーが発生するリスクはありません。 ディレクトリ同期は、オンプレミス環境とオンライン環境の間でこれらのアカウントをミラーリングするのに役立ちます。 ディレクトリ同期を使用すると、ユーザーは環境ごとに新しい情報を記憶する必要が生じ、アカウントを 2 回作成または更新する必要はありません。 ディレクトリ同期のために [オンプレミス ディレクトリを準備](prepare-for-directory-synchronization.md) する必要があります。
  
![ディレクトリ同期を使用してオンプレミスとオンラインのユーザー アカウント情報を同期する](../media/microsoft-365-integration/directory-synchronization.png)
  
ユーザーがオンプレミスの資格情報を使用して Microsoft 365 にログオンする場合は、SSO を構成できます。 SSO を使用すると、Microsoft 365 はユーザー認証のためにオンプレミス環境を信頼するように構成されています。
  
![シングル サインオンでは、オンプレミス環境とオンライン環境の両方で同じアカウントを利用できます。](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>パスワード ハッシュ同期またはパススルー認証 (PTA) の使用とディレクトリの同期

ユーザーは、自分のユーザー アカウント (domain\username) を使用してオンプレミス環境にログオンします。 Microsoft 365 に移動する場合は、仕事用または学校用のアカウントで再度ログオンする必要があります (user@domain.com)。 ユーザー名は、両方の環境で同じです。 PHS または PTA を追加すると、ユーザーは両方の環境で同じパスワードを持ちますが、Microsoft 365 にログオンするときにそれらの資格情報を再度指定する必要があります。 PHS とのディレクトリ同期は、最も一般的に使用されるディレクトリ同期です。

ディレクトリ同期を設定するには、Azure AD接続を使用します。 手順については [、「Microsoft 365](set-up-directory-synchronization.md) および Azure のディレクトリ同期をセットアップする」および「 [高速AD接続する」を参照してください](/azure/active-directory/hybrid/how-to-connect-install-express)。

[Microsoft 365](prepare-for-directory-synchronization.md)へのディレクトリ同期の準備の詳細について説明します。

### <a name="directory-synchronization-with-sso"></a>SSO とのディレクトリ同期

ユーザーは、自分のユーザー アカウントを使用してオンプレミス環境にログオンします。 Microsoft 365 に移動すると、自動的にログオンするか、オンプレミス環境 (domain\username) で使用するのと同じ資格情報を使用してログオンします。

SSO を設定するには、Azure AD使用します。 手順については、「Azure AD Connect のカスタム [インストール」を参照してください](/azure/active-directory/hybrid/how-to-connect-install-custom)。

詳細については、「シングル サインオン [」を参照してください](/azure/active-directory/manage-apps/what-is-single-sign-on)。

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD Connect は、以前のバージョンの ID 統合ツール (DirSync や Azure AD同期など) を置き換える。Azure Active Directory Sync から Azure Active Directory Sync から Azure AD接続に更新する場合は、アップグレード [手順を参照してください](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started)。 

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)