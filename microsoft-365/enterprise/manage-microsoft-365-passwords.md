---
title: ユーザー Microsoft 365パスワードの管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: ユーザー アカウントのパスワードをMicrosoft 365する方法について説明します。
ms.openlocfilehash: ac83ef8a52bd0f0c3a6a8d1c0164c6eb6c0a4f4b20045d5c23ad2c1fb7a6b6da
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53899309"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>ユーザー Microsoft 365パスワードの管理

*この記事は、Microsoft 365 Enterprise と Office 365 Enterprise の両方に適用されます。*

ID 構成にMicrosoft 365、ユーザー アカウント のパスワードを管理できます。 ユーザー アカウントは[、Microsoft 365 管理センター、Active](../admin/add-users/index.yml)Directory ドメイン サービス (AD DS)、または Azure Active Directory (Azure AD) 管理センターで管理できます。

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>ユーザー アカウントのパスワードを管理する場所と方法を計画する

ユーザー アカウントを管理する場所と方法は、ユーザー アカウントに使用する id モデルによってMicrosoft 365。 2 つのモデルは、クラウド専用とハイブリッドです。
  
### <a name="cloud-only"></a>クラウド専用

ユーザー アカウントのパスワードは、次の場所で管理します。

- [Microsoft 365 管理センター](../admin/add-users/index.yml)
- Azure AD管理センター
    
### <a name="hybrid"></a>ハイブリッド

ハイブリッド ID を使用すると、AD DS に保存されます。そのため、ユーザー アカウントのパスワードを管理するには、オンプレミスの DS ADを使用する必要があります。 Azure AD が既にハッシュ化されたバージョンのハッシュバージョンを AD DS に格納するパスワード ハッシュ同期 (PHS) を使用する場合でも、ユーザーとユーザーは AD DS でパスワードを管理する必要があります。

パスワード [の書き戻し](#pw_writeback)を使用すると、ユーザーは Azure ADを使用して DS パスワードを変更AD。

## <a name="prevent-bad-passwords"></a>脆弱なパスワードを防止する

すべてのユーザーが [Microsoft のパスワードのガイダンス](https://www.microsoft.com/research/publication/password-guidance)を使用してユーザー アカウントのパスワードを作成する必要があります。

ユーザーがパスワードを容易に作成するのを防ぐため、Azure AD のパスワード保護を使用します。この機能では、グローバル禁止パスワード リストと指定したカスタムの禁止パスワード リスト (省略可能) の両方を使用します。 たとえば、次のような組織固有の用語を指定できます。

- ブランド名
- 製品名
- 場所 (たとえば、会社の本部など)
- 会社固有の内部用語
- 会社固有の意味を持つ略語

クラウドとオンプレミスの DS[](/azure/active-directory/authentication/concept-password-ban-bad)で、悪いパスワードを[ADできます](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)。

## <a name="simplify-user-sign-in"></a>ユーザー サインインを簡素化する

Azure AD シームレス シングル Sign-On (Azure AD シームレス SSO) は PHS および Pass-Through 認証 (PTA) と連携して、ユーザーがパスワードを入力せずに Azure AD ユーザー アカウントを使用するサービスにサインインできます。多くの場合、ユーザー名を入力する必要があります。 これにより、ユーザーは Office 365 などのクラウド ベースのアプリケーションに簡単にアクセスできるようになります。ID フェデレーション サーバーのような追加のオンプレミス コンポーネントは不要です。

Azure AD Connect ツールを使用して Azure AD シームレス SSO を構成します。 「[Azure Active Directory シームレス シングル サインオン: クイック スタート](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)」を参照してください。

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>DS に対するパスワード更新AD簡略化する

パスワードの書き戻しを使用すると、ユーザーが Azure AD 経由でパスワードをリセットし、そのパスワードを DS にADできます。 ユーザーは、パスワードを更新するためにオンプレミスの DS にADする必要はありません。 これは、オンプレミスのネットワークへのリモート アクセス接続を持たないローミング ユーザーやリモート ユーザーにとって役立ちます。

パスワードの書き戻しは、Azure AD Identity Protection 機能 (アカウント侵害が発生する可能性が高い危険が検出された場合にオンプレミス パスワードの変更をユーザーに義務付けるなど) を最大限に活用するために必要です。

その他の情報と構成手順については、「[Azure AD SSPR とパスワード書き戻し](/azure/active-directory/active-directory-passwords-writeback)」を参照してください。

>[!Note]
>最適なエクスペリエンスとリリースされた新機能を利用できるようにするため、Azure AD Connect の最新バージョンにアップグレードします。詳細については、「[Azure AD Connect のカスタム インストール](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)」を参照してください。
>

## <a name="simplify-password-resets"></a>パスワード再設定を簡素化する

セルフサービス パスワードリセット (SSPR) を使用すると、ユーザーはパスワードまたはアカウントをリセットまたはロック解除できます。 誤用または悪用について警告するため、通知と共に、ユーザーがいつシステムにアクセスしたかを追跡する詳細なレポート作成機能を使用できます。 パスワードのリセットを [展開する前に](#pw_writeback) 、パスワードの書き戻しを有効にする必要があります。

「[セルフサービスによるパスワードのリセットを適切にロールアウトする方法](/azure/active-directory/authentication/howto-sspr-deployment)」を参照してください。