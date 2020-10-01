---
title: Microsoft 365 ユーザーアカウントのパスワードを管理する
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
description: Microsoft 365 ユーザーアカウントのパスワードを管理する方法について説明します。
ms.openlocfilehash: af64002ad54b517a6e8f0b687a00d6bed9ab0214
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328511"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>Microsoft 365 ユーザーアカウントのパスワードを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Id の構成に応じて、Microsoft 365 のユーザーアカウントのパスワードをさまざまな方法で管理できます。 ユーザーアカウントは、 [Microsoft 365 管理センター](https://docs.microsoft.com/microsoft-365/admin/add-users/)、Active Directory ドメインサービス (AD DS)、または Azure Active Directory (azure AD) 管理センターで管理できます。

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>ユーザーアカウントのパスワードを管理する場所と方法を計画します。

ユーザーアカウントを管理する場所と方法は、Microsoft 365 で使用する id モデルによって異なります。 2つのモデルは、クラウド専用でハイブリッドです。
  
### <a name="cloud-only"></a>クラウド専用

ユーザーアカウントのパスワードを管理するには、次のようにします。

- [Microsoft 365 管理センター](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- Azure AD 管理センター
    
### <a name="hybrid"></a>ハイブリッド

ハイブリッド id では、パスワードが AD DS に格納されるため、オンプレミスの AD DS ツールを使用してユーザーアカウントのパスワードを管理する必要があります。 パスワードハッシュ同期 (PHS) を使用している場合でも、Azure AD は AD DS で既にハッシュされたバージョンのハッシュ化されたバージョンを格納し、ユーザーは AD DS で自分のパスワードを管理する必要があります。

[パスワードの書き戻し](#pw_writeback)を使用すると、ユーザーは Azure ad を使用して ad DS のパスワードを変更できます。

## <a name="prevent-bad-passwords"></a>脆弱なパスワードを防止する

すべてのユーザーが [Microsoft のパスワードのガイダンス](https://www.microsoft.com/research/publication/password-guidance)を使用してユーザー アカウントのパスワードを作成する必要があります。

ユーザーがパスワードを容易に作成するのを防ぐため、Azure AD のパスワード保護を使用します。この機能では、グローバル禁止パスワード リストと指定したカスタムの禁止パスワード リスト (省略可能) の両方を使用します。 たとえば、次のような組織固有の用語を指定できます。

- ブランド名
- 製品名
- 場所 (たとえば、会社の本部など)
- 会社固有の内部用語
- 会社固有の意味を持つ略語

[クラウド内](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)の無効なパスワードを禁止し、[オンプレミスの AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)に対して無効にすることができます。

## <a name="simplify-user-sign-in"></a>ユーザー サインインを簡素化する

Azure ad シームレスシングルサインオン (Azure AD シームレス SSO) は、PHS とパススルー認証 (PTA) を使用して動作し、ユーザーがパスワードを入力しなくても、Azure AD ユーザーアカウントを使用するサービスにサインインしたり、多くの場合はユーザー名を入力したりすることができます。 これにより、ユーザーは Office 365 などのクラウド ベースのアプリケーションに簡単にアクセスできるようになります。ID フェデレーション サーバーのような追加のオンプレミス コンポーネントは不要です。

Azure AD Connect ツールを使用して Azure AD シームレス SSO を構成します。 「[Azure Active Directory シームレス シングル サインオン: クイック スタート](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)」を参照してください。

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>AD DS へのパスワードの更新を簡素化する

パスワードの書き戻しを使用すると、ユーザーが Azure AD 経由でパスワードをリセットできるようになります。これは、AD DS にレプリケートされます。 ユーザーは、オンプレミスの AD DS にアクセスしてパスワードを更新する必要はありません。 これは、オンプレミスのネットワークへのリモート アクセス接続を持たないローミング ユーザーやリモート ユーザーにとって役立ちます。

パスワードの書き戻しは、Azure AD Identity Protection 機能 (アカウント侵害が発生する可能性が高い危険が検出された場合にオンプレミス パスワードの変更をユーザーに義務付けるなど) を最大限に活用するために必要です。

その他の情報と構成手順については、「[Azure AD SSPR とパスワード書き戻し](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)」を参照してください。

>[!Note]
>最適なエクスペリエンスとリリースされた新機能を利用できるようにするため、Azure AD Connect の最新バージョンにアップグレードします。詳細については、「[Azure AD Connect のカスタム インストール](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)」を参照してください。
>

## <a name="simplify-password-resets"></a>パスワード再設定を簡素化する

セルフサービスによるパスワードのリセット (SSPR) により、ユーザーは自分のパスワードまたはアカウントをリセットまたはロック解除することができます。 誤用または悪用について警告するため、通知と共に、ユーザーがいつシステムにアクセスしたかを追跡する詳細なレポート作成機能を使用できます。 パスワードのリセットを展開するには、 [パスワードの書き戻し](#pw_writeback) を有効にする必要があります。

「[セルフサービスによるパスワードのリセットを適切にロールアウトする方法](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)」を参照してください。

