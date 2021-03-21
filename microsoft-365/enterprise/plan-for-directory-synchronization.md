---
title: Microsoft 365 のハイブリッド ID とディレクトリ同期
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Microsoft 365、Active Directory ドメイン サービスのクリーンアップ、および Azure Active Directory Connect ツールとのディレクトリ同期について説明します。
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927546"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a>Microsoft 365 のハイブリッド ID とディレクトリ同期

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ビジネス ニーズと技術的要件に応じて、ハイブリッド ID モデルとディレクトリ同期は、Microsoft 365 を採用している企業のお客様にとって最も一般的な選択肢です。 ディレクトリ同期を使用すると、Active Directory ドメイン サービス (AD DS) の ID を管理し、ユーザー アカウント、グループ、および連絡先に対する更新はすべて、Microsoft 365 サブスクリプションの Azure Active Directory (Azure AD) テナントに同期されます。

>[!Note]
>DS ADが初めて同期される場合、Microsoft 365 ライセンスが自動的に割り当てられるのではなく、電子メールなどの Microsoft 365 サービスにアクセスできません。 最初に使用場所を割り当てる必要があります。 次に、グループ メンバーシップを使用して、個別または動的にこれらのユーザー アカウントにライセンスを割り当てる。
>

## <a name="authentication-for-hybrid-identity"></a>ハイブリッド ID の認証

ハイブリッド ID モデルを使用する場合、認証には次の 2 種類があります。

- 管理された認証

  Azure ADは、ローカルに保存されたハッシュ バージョンのパスワードを使用して認証プロセスを処理するか、オンプレミスのソフトウェア エージェントに資格情報を送信して、オンプレミスの AD DS によって認証されます。

- フェデレーション認証

  Azure AD認証を要求するクライアント コンピューターを別の ID プロバイダーにリダイレクトします。

### <a name="managed-authentication"></a>管理された認証

管理認証には、次の 2 種類があります。

- パスワード ハッシュ同期 (PHS)

  Azure AD認証自体を実行します。

- パススルー認証 (PTA)

  Azure AD DS AD認証を実行しています。


#### <a name="password-hash-synchronization-phs"></a>パスワード ハッシュ同期 (PHS)

PHS では、DS ユーザー AD Microsoft 365 と同期し、オンプレミスでユーザーを管理します。 ユーザー パスワードのハッシュは、AD DS から Azure AD に同期され、ユーザーはオンプレミスとクラウドで同じパスワードを使用できます。 これは、Azure ADで DS ID の認証を有効にする最も簡単なAD。 

![パスワード ハッシュ同期 (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

オンプレミスでパスワードを変更またはリセットすると、新しいパスワード ハッシュが Azure AD に同期され、ユーザーはクラウド リソースとオンプレミス リソースに対して常に同じパスワードを使用できます。 ユーザー のパスワードは、Azure サーバーに送信AD、クリア テキストで azure AD保存されません。 Id Protection など、Azure ADの一部のプレミアム機能では、どの認証方法が選択されているに関係なく PHS が必要です。
  
詳細 [については、「適切な認証方法の選択](/azure/active-directory/hybrid/choose-ad-authn) 」を参照してください。
  
#### <a name="pass-through-authentication-pta"></a>パススルー認証 (PTA)

PTA は、1 つ以上のオンプレミス サーバーで実行されているソフトウェア エージェントを使用して Azure AD 認証サービスの簡単なパスワード検証を提供し、AD DS を使用してユーザーを直接検証します。 PTA では、DS ユーザー AD Microsoft 365 と同期し、オンプレミスでユーザーを管理します。 

![パススルー認証 (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

PTA を使用すると、ユーザーはオンプレミスのアカウントとパスワードを使用して、オンプレミスと Microsoft 365 の両方のリソースとアプリケーションにサインインできます。 この構成では、Azure サーバーにパスワード ハッシュを格納せずに、AD DS に対してユーザーのパスワードを直接検証AD。 

PTA は、セキュリティ要件を持つ組織でも、オンプレミスのユーザー アカウントの状態、パスワード ポリシー、ログオン時間を直ちに適用します。 
  
詳細 [については、「適切な認証方法の選択](/azure/active-directory/hybrid/choose-ad-authn) 」を参照してください。
  
### <a name="federated-authentication"></a>フェデレーション認証

フェデレーション認証は、主に、より複雑な認証要件を持つ大規模なエンタープライズ組織向けです。 AD DS ID は Microsoft 365 と同期され、ユーザー アカウントはオンプレミスで管理されます。 フェデレーション認証では、ユーザーはオンプレミスとクラウドで同じパスワードを持ち、Microsoft 365 を使用するために再びサインインする必要はありません。 

フェデレーション認証は、スマートカードベース認証やサードパーティの多要素認証などの追加の認証要件をサポートできます。通常、組織が Azure AD でネイティブにサポートされていない認証要件を持っている場合に必要です。
 
詳細 [については、「適切な認証方法の選択](/azure/active-directory/hybrid/choose-ad-authn) 」を参照してください。
  
#### <a name="third-party-authentication-and-identity-providers"></a>サード パーティ認証と ID プロバイダー

オンプレミスのディレクトリ オブジェクトは Microsoft 365 に同期され、クラウド リソース アクセスは主にサード パーティ ID プロバイダー (IdP) によって管理されます。 組織でサード パーティのフェデレーション ソリューションを使用している場合は、サード パーティのフェデレーション ソリューションが Azure AD と互換性がある場合は、Microsoft 365 のソリューションを使用してサインオンを構成できます。
  
詳細については [、「Azure ADフェデレーション互換性リスト](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) 」を参照してください。
  
## <a name="ad-ds-preparation"></a>AD DS の準備

同期を使用して Microsoft 365 へのシームレスな移行を実現するには、Microsoft 365 ディレクトリ同期の展開を開始する前に、AD DS フォレストを準備する必要があります。
  
ディレクトリの準備では、次のタスクに重点を置く必要があります。

- 重複する **proxyAddress 属性と** **userPrincipalName 属性を削除** します。
- 有効な **userPrincipalName 属性を使用して、空の userPrincipalName** 属性と無効な **userPrincipalName 属性を更新** します。
- **givenName**、 surname ( **sn** ) 、 **sAMAccountName**、 **displayName**、 **mail**、 **proxyAddresses**、 **mailNickname**、 **userPrincipalName** 属性の無効で疑いがある文字を削除します。 属性の準備の詳細については、「Azure Active Directory 同期ツールによって同期される属性の一覧」 [を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=396719)。

    > [!NOTE]
    > これらは、Azure が Connect で同期AD属性です。 
  
## <a name="multi-forest-deployment-considerations"></a>複数フォレストの展開に関する考慮事項

複数のフォレストと SSO オプションの場合は、Azure のカスタム インストール [を使用して](/azure/active-directory/hybrid/how-to-connect-install-custom)接続ADします。
  
組織に認証用の複数のフォレスト (ログオン フォレスト) がある場合は、次の情報を強くお勧めします。
  
- **フォレストの統合を検討してください。** 一般に、複数のフォレストを維持するために必要なオーバーヘッドが大きくなります。 組織に個別のフォレストの必要性を指示するセキュリティ上の制約がない限り、オンプレミス環境の簡素化を検討してください。
- **プライマリ ログオン フォレストでのみ使用します。** Microsoft 365 の初期ロールアウトでは、プライマリ ログオン フォレストにのみ Microsoft 365 を展開する必要があります。 

マルチフォレスト AD DS 展開を統合できない場合、または他のディレクトリ サービスを使用して ID を管理できない場合は、Microsoft またはパートナーの助けを借りてこれらを同期できます。
  
詳細 [については、「トポロジ for Azure AD接続」](/azure/active-directory/hybrid/plan-connect-topologies) を参照してください。
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a>ディレクトリ同期に依存する機能
  
ディレクトリ同期は、次の機能に必要です。
  
- Azure AD シームレス シングル Sign-On (SSO)
- Skype の共存
- 以下を含む Exchange ハイブリッド展開。
  - オンプレミスの Exchange 環境と Microsoft 365 の間で完全に共有されたグローバル アドレス一覧 (GAL)。
  - 異なるメール システムからの GAL 情報の同期。
  - Microsoft 365 サービス製品にユーザーを追加したり、Microsoft 365 サービスからユーザーを削除したりする機能。 これには、次の情報が必要です。
  - ディレクトリ同期のセットアップ中に、2 つの方法で同期を構成する必要があります。 既定では、ディレクトリ同期ツールはディレクトリ情報のみをクラウドに書き込む。 2 者間同期を構成する場合は、限られた数のオブジェクト属性がクラウドからコピーされ、ローカルの AD DS に書き戻されるように、書き戻し機能を有効にします。 書き戻しは Exchange ハイブリッド モードとも呼ばれます。 
  - オンプレミスの Exchange ハイブリッド展開
  - 他のユーザー メールボックスをオンプレミスに維持しながら、一部のユーザー メールボックスを Microsoft 365 に移動する機能。
  - オンプレミスの差出人セーフ リストとブロックされた送信者は、Microsoft 365 にレプリケートされます。
  - 基本的な委任と電子メールの代理送信機能。
  - 統合されたオンプレミスのスマート カードまたは多要素認証ソリューションがあります。
- 写真、サムネイル、会議室、セキュリティ グループの同期

## <a name="next-step"></a>次の手順

ハイブリッド ID を展開する準備ができたら、「ディレクトリ同期の準備 [」を参照してください](prepare-for-directory-synchronization.md)。
