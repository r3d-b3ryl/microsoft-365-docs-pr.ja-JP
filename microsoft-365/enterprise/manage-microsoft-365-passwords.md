---
title: Microsoft 365 ユーザー アカウントのパスワードを管理する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: overview
ms.prod: office-online-server
ms.localizationpriority: medium
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
description: ユーザー アカウントのパスワードMicrosoft 365管理する方法について説明します。
ms.openlocfilehash: 689f88c2380f0655af70cea08404ed7163fa1239
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65094396"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>Microsoft 365 ユーザー アカウントのパスワードを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365ユーザー アカウントのパスワードは、ID の構成に応じていくつかの方法で管理できます。 ユーザー アカウントは[、Microsoft 365 管理センター、Active Directory Domain Services](/admin) (AD DS)、またはAzure Active Directory (Azure AD) 管理センターで管理できます。

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>ユーザー アカウントのパスワードを管理する場所と方法を計画する

ユーザー アカウントをどこでどのように管理できるかは、Microsoft 365に使用する ID モデルによって異なります。 2 つのモデルはクラウド専用とハイブリッドです。
  
### <a name="cloud-only"></a>クラウド専用

ユーザー アカウントのパスワードは、次の手順で管理します。

- [Microsoft 365 管理センター](/admin)
- Azure AD管理センター
    
### <a name="hybrid"></a>ハイブリッド

ハイブリッド ID では、パスワードは AD DS に格納されるため、オンプレミスの AD DS ツールを使用してユーザー アカウントのパスワードを管理する必要があります。 パスワード ハッシュ同期 (PHS) を使用する場合でも、既にハッシュされたバージョンのハッシュバージョンが AD DS に格納Azure AD、ユーザーとユーザーは AD DS でパスワードを管理する必要があります。

[パスワード ライトバック](#pw_writeback)を使用すると、ユーザーはAzure ADを使用して AD DS パスワードを変更できます。

## <a name="prevent-bad-passwords"></a>脆弱なパスワードを防止する

すべてのユーザーが [Microsoft のパスワードのガイダンス](https://www.microsoft.com/research/publication/password-guidance)を使用してユーザー アカウントのパスワードを作成する必要があります。

ユーザーがパスワードを容易に作成するのを防ぐため、Azure AD のパスワード保護を使用します。この機能では、グローバル禁止パスワード リストと指定したカスタムの禁止パスワード リスト (省略可能) の両方を使用します。 たとえば、次のような組織固有の用語を指定できます。

- ブランド名
- 製品名
- 場所 (たとえば、会社の本部など)
- 会社固有の内部用語
- 会社固有の意味を持つ略語

クラウドと[オンプレミスの AD DS](/azure/active-directory/authentication/concept-password-ban-bad-on-premises) [では](/azure/active-directory/authentication/concept-password-ban-bad)、不適切なパスワードを禁止できます。

## <a name="simplify-user-sign-in"></a>ユーザー サインインを簡素化する

Azure ADシームレス シングル Sign-On (Azure AD シームレス SSO) は、PHS およびPass-Through認証 (PTA) と連携して動作し、ユーザーがパスワードを入力しなくてもAzure ADユーザー アカウントを使用するサービスにサインインできるようにし、多くの場合、ユーザー名を入力できます。 これにより、ユーザーは Office 365 などのクラウド ベースのアプリケーションに簡単にアクセスできるようになります。ID フェデレーション サーバーのような追加のオンプレミス コンポーネントは不要です。

Azure AD Connect ツールを使用して Azure AD シームレス SSO を構成します。 「[Azure Active Directory シームレス シングル サインオン: クイック スタート](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)」を参照してください。

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>AD DS のパスワード更新を簡略化する

パスワード ライトバックを使用すると、ユーザーがAzure ADを使用してパスワードをリセットし、AD DS にレプリケートできます。 ユーザーは、パスワードを更新するためにオンプレミスの AD DS にアクセスする必要はありません。 これは、オンプレミスのネットワークへのリモート アクセス接続を持たないローミング ユーザーやリモート ユーザーにとって役立ちます。

パスワードの書き戻しは、Azure AD Identity Protection 機能 (アカウント侵害が発生する可能性が高い危険が検出された場合にオンプレミス パスワードの変更をユーザーに義務付けるなど) を最大限に活用するために必要です。

その他の情報と構成手順については、「[Azure AD SSPR とパスワード書き戻し](/azure/active-directory/active-directory-passwords-writeback)」を参照してください。

>[!Note]
>最適なエクスペリエンスとリリースされた新機能を利用できるようにするため、Azure AD Connect の最新バージョンにアップグレードします。詳細については、「[Azure AD Connect のカスタム インストール](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)」を参照してください。
>

## <a name="simplify-password-resets"></a>パスワード再設定を簡素化する

セルフサービス パスワード リセット (SSPR) を使用すると、ユーザーは自分のパスワードまたはアカウントをリセットまたはロック解除できます。 誤用または悪用について警告するため、通知と共に、ユーザーがいつシステムにアクセスしたかを追跡する詳細なレポート作成機能を使用できます。 パスワード リセットを展開するには、 [パスワード ライトバック](#pw_writeback) を有効にする必要があります。

「[セルフサービスによるパスワードのリセットを適切にロールアウトする方法](/azure/active-directory/authentication/howto-sspr-deployment)」を参照してください。