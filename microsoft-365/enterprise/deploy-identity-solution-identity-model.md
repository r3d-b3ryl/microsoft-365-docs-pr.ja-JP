---
title: 手順 1. クラウド ID モデルを決定する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: 手順 1. Microsoft クラウド ID モデルを決定する
ms.openlocfilehash: 41604ebb08104f802e33023763e9771d2b6acfda
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65101273"
---
# <a name="step-1-determine-your-cloud-identity-model"></a>手順 1. クラウド ID モデルを決定する

Microsoft 365では、Microsoft 365 サブスクリプションに含まれるクラウドベースのユーザー ID と認証サービスであるAzure Active Directory (Azure AD) を使用して、Microsoft 365の ID と認証を管理します。 組織のユーザー アクセスとアクセス許可Microsoft 365管理するには、ID インフラストラクチャを正しく構成することが不可欠です。

開始する前に、Microsoft 365 の ID モデルと認証の概要についてこのビデオをご覧ください。

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

最初の計画の選択は、クラウド ID モデルです。

## <a name="microsoft-cloud-identity-models"></a>Microsoft クラウド ID モデル

ユーザー アカウントを計画するには、まず、Microsoft 365の 2 つの ID モデルを理解する必要があります。 組織の ID はクラウド内でのみ管理することも、オンプレミスの Active Directory Domain Services (AD DS) ID を維持して、ユーザーがクラウド サービスにアクセスするときに認証に使用Microsoft 365することもできます。

2 種類の ID と、その最適さと利点を次に示します。

| 属性 | クラウド専用 ID | ハイブリッド ID |
|:-------|:-----|:-----|
| **定義** | ユーザー アカウントは、Microsoft 365 サブスクリプションのAzure AD テナントにのみ存在します。 | ユーザー アカウントは AD DS に存在し、コピーはMicrosoft 365 サブスクリプションのAzure AD テナントにも存在します。 Azure ADのユーザー アカウントには、既にハッシュされた AD DS ユーザー アカウントパスワードのハッシュバージョンも含まれる場合があります。 |
| **ユーザー資格情報Microsoft 365認証する方法** | Microsoft 365 サブスクリプションのAzure AD テナントは、クラウド ID アカウントを使用して認証を実行します。 | Microsoft 365 サブスクリプションのAzure AD テナントは、認証プロセスを処理するか、ユーザーを別の ID プロバイダーにリダイレクトします。 |
| **最適シナリオ** | オンプレミスの AD DS を持っていない、または必要ない組織。 | AD DS または別の ID プロバイダーを使用している組織。 |
| **最大の利点** | 使いやすいです。 追加のディレクトリ ツールやサーバーは必要ありません。 | ユーザーは、オンプレミスまたはクラウドベースのリソースにアクセスするときに同じ資格情報を使用できます。 |
||||

## <a name="cloud-only-identity"></a>クラウド専用 ID

クラウドのみの ID は、Azure AD にのみ存在するユーザー アカウントを使用します。 クラウドのみの ID は、通常、オンプレミス サーバーを持たない小規模な組織、または AD DS を使用してローカル ID を管理しない小規模な組織で使用されます。

クラウドのみの ID の基本的なコンポーネントを次に示します。

![クラウドのみの ID の基本的なコンポーネント。](../media/about-microsoft-365-identity/cloud-only-identity.png)

オンプレミスとリモート (オンライン) の両方のユーザーは、Azure ADユーザー アカウントとパスワードを使用して、クラウド サービスMicrosoft 365アクセスします。 Azure AD は、保存されたユーザー アカウントとパスワードに基づいて、ユーザー資格情報を認証します。

### <a name="administration"></a>管理
ユーザー アカウントはAzure ADにのみ格納されるため、[Microsoft 365 管理センター](/admin)や[Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)などのツールを使用してクラウド ID を管理します。

## <a name="hybrid-identity"></a>ハイブリッド ID

ハイブリッド ID は、オンプレミスの AD DS で作成されたアカウントを使用し、Microsoft 365 サブスクリプションのAzure AD テナントにコピーを持ちます。 ほとんどの変更は、 [特定のアカウント属性](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)を除き、一方向にのみフローします。 AD DS ユーザー アカウントに加えた変更は、Azure AD内のコピーに同期されます。

Azure AD Connectは、継続的なアカウント同期を提供します。 オンプレミス サーバー上で実行され、AD DS の変更が確認され、それらの変更がAzure ADに転送されます。 Azure AD Connectでは、同期されるアカウントと、パスワード ハッシュ同期 (PHS) と呼ばれるハッシュバージョンのユーザー パスワードを同期するかどうかをフィルター処理する機能が提供されます。

ハイブリッド ID を導入した場合、オンプレミスの AD DS がアカウント情報の信頼できるソースとなります。 つまり、主にオンプレミスで管理タスクを実行し、その後、Azure ADに同期されます。

ハイブリッド ID のコンポーネントを次に示します。

![ハイブリッド ID のコンポーネント。](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD テナントには、AD DS アカウントのコピーがあります。 この構成では、クラウド サービスにアクセスするオンプレミスユーザーとリモート ユーザーの両方がAzure ADに対して認証Microsoft 365。

> [!NOTE]
> ハイブリッド ID のユーザー アカウントを同期するには、常にAzure AD Connectを使用する必要があります。 ライセンスの割り当てとグループ管理の実行、アクセス許可の構成、およびユーザー アカウントを含むその他の管理タスクを実行するには、Azure ADに同期されたユーザー アカウントが必要です。

### <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a>Microsoft 365のハイブリッド ID とディレクトリの同期

ビジネス ニーズと技術的要件に応じて、ハイブリッド ID モデルとディレクトリ同期は、Microsoft 365を採用しているエンタープライズ顧客にとって最も一般的な選択肢です。 ディレクトリ同期を使用すると、Active Directory Domain Services (AD DS) 内の ID を管理し、ユーザー アカウント、グループ、および連絡先に対するすべての更新が、Microsoft 365 サブスクリプションのAzure Active Directory (Azure AD) テナントに同期されます。

>[!Note]
>AD DS ユーザー アカウントが初めて同期されると、自動的にMicrosoft 365 ライセンスが割り当てられず、メールなどのMicrosoft 365サービスにアクセスできません。 最初に、使用場所を割り当てる必要があります。 次に、グループ メンバーシップを使用して、これらのユーザー アカウントに個別または動的にライセンスを割り当てます。
>

#### <a name="authentication-for-hybrid-identity"></a>ハイブリッド ID の認証

ハイブリッド ID モデルを使用する場合、認証には次の 2 種類があります。

- 管理された認証

  Azure ADは、ローカルに格納されたハッシュバージョンのパスワードを使用して認証プロセスを処理するか、オンプレミスの AD DS によって認証されるオンプレミスのソフトウェア エージェントに資格情報を送信します。

- フェデレーション認証

  Azure AD認証を要求しているクライアント コンピューターを別の ID プロバイダーにリダイレクトします。

#### <a name="managed-authentication"></a>管理された認証

マネージド認証には、次の 2 種類があります。

- パスワード ハッシュ同期 (PHS)

  Azure ADは認証自体を実行します。

- パススルー認証 (PTA)

  AD DS に認証を実行Azure AD。


##### <a name="password-hash-synchronization-phs"></a>パスワード ハッシュ同期 (PHS)

PHS では、AD DS ユーザー アカウントをMicrosoft 365と同期し、オンプレミスでユーザーを管理します。 ユーザーパスワードのハッシュは、ユーザーがオンプレミスとクラウドで同じパスワードを持つよう、AD DS からAzure ADに同期されます。 これは、Azure ADで AD DS ID の認証を有効にする最も簡単な方法です。 

![パスワード ハッシュ同期 (PHS)。](../media/plan-for-directory-synchronization/phs-authentication.png)

パスワードがオンプレミスで変更またはリセットされると、新しいパスワード ハッシュがAzure ADに同期されるため、ユーザーはクラウド リソースとオンプレミス リソースに対して常に同じパスワードを使用できます。 ユーザー パスワードは、Azure ADに送信されたり、クリア テキストでAzure ADに保存されたりすることはありません。 Identity Protection など、Azure ADの一部のプレミアム機能では、選択されている認証方法に関係なく PHS が必要です。
  
詳細については [、適切な認証方法の選択](/azure/active-directory/hybrid/choose-ad-authn) に関するページを参照してください。
  
##### <a name="pass-through-authentication-pta"></a>パススルー認証 (PTA)

PTA では、1 つ以上のオンプレミス サーバーで実行されているソフトウェア エージェントを使用してAzure AD認証サービスに対して簡単なパスワード検証を提供し、AD DS でユーザーを直接検証します。 PTA では、AD DS ユーザー アカウントをMicrosoft 365と同期し、オンプレミスでユーザーを管理します。 

![パススルー認証 (PTA)。](../media/plan-for-directory-synchronization/pta-authentication.png)

PTA を使用すると、ユーザーはオンプレミスのアカウントとパスワードを使用して、オンプレミスとMicrosoft 365の両方のリソースとアプリケーションにサインインできます。 この構成では、パスワード ハッシュをAzure ADに格納せずに、ユーザーのパスワードをオンプレミスの AD DS に対して直接検証します。 

PTA は、セキュリティ要件を持つ組織が、オンプレミスのユーザー アカウントの状態、パスワード ポリシー、およびログオン時間を直ちに適用する場合でもあります。 
  
詳細については [、適切な認証方法の選択](/azure/active-directory/hybrid/choose-ad-authn) に関するページを参照してください。
  
##### <a name="federated-authentication"></a>フェデレーション認証

フェデレーション認証は、主に、より複雑な認証要件を持つ大企業の組織向けです。 AD DS ID はMicrosoft 365と同期され、ユーザー アカウントはオンプレミスで管理されます。 フェデレーション認証では、ユーザーはオンプレミスとクラウドで同じパスワードを持ち、Microsoft 365を使用するためにもう一度サインインする必要はありません。 

フェデレーション認証は、スマートカード ベースの認証やサード パーティの多要素認証などの追加の認証要件をサポートできます。通常、組織でネイティブにサポートされていない認証要件がAzure ADでサポートされている場合に必要です。
 
詳細については [、適切な認証方法の選択](/azure/active-directory/hybrid/choose-ad-authn) に関するページを参照してください。
  
サード パーティの認証および ID プロバイダーの場合、オンプレミスのディレクトリ オブジェクトは、主にサード パーティ ID プロバイダー (IdP) によって管理されるMicrosoft 365およびクラウド リソース アクセスに同期される場合があります。 組織でサード パーティのフェデレーション ソリューションを使用している場合は、サード パーティのフェデレーション ソリューションがAzure ADと互換性がある場合に備えて、Microsoft 365用にそのソリューションでサインオンを構成できます。
  
詳細については、[Azure ADフェデレーション互換性の一覧](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility)を参照してください。
  
### <a name="administration"></a>管理

元の権限のあるユーザー アカウントはオンプレミスの AD DS に格納されるため、AD DS を管理するのと同じツールを使用して ID を管理します。

Microsoft 365にMicrosoft 365 管理センターまたは PowerShell を使用して、Azure ADで同期されたユーザー アカウントを管理することはありません。

## <a name="next-step"></a>次の手順

[![Microsoft 365特権アカウントを保護する](../media/deploy-identity-solution-overview/protect-your-global-administrator-accounts.png)](protect-your-global-administrator-accounts.md)

[手順 2 に](protect-your-global-administrator-accounts.md)進み、グローバル管理者アカウントをセキュリティで保護します。
