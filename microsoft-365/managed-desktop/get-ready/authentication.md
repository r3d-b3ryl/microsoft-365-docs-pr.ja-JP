---
title: Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する
description: Azure クライアントが認証を提供するためにオンプレミスAD通信を行AD重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f6b1e257fd767fa112fddb41d773065b8002a2a3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909192"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する

Microsoft Managed Desktop では、デバイスは Azure Active Directory (Azure Active Directory) に自動的に参加AD。 このため、オンプレミスの Active Directory を使用している場合は、Azure AD に参加しているデバイスがオンプレミスの Active Directory と通信できるよう、いくつかのことを確認する必要があります。 

> [!NOTE]  
> *ハイブリッド* Azure AD参加は、Microsoft Managed Desktop ではサポートされていません。

Azure Active Directory を使用すると、ユーザーはシングル Sign-On (SSO) を利用できます。つまり、通常、リソースを使用する度に資格情報を提供する必要がなされません。

Azure Active Directory への参加の詳細については、「How [to: Plan your Azure AD実装」を参照してください](/azure/active-directory/devices/azureadjoin-plan)。 Azure AD に参加しているデバイスでのシングル Sign-On (SSO) のバックグラウンド情報については [、「Azure](/azure/active-directory/devices/azuread-join-sso#how-it-works)AD 参加デバイスでのオンプレミス リソースへの SSO の動作」を参照してください。


この記事では、ローカルの Active Directory 接続に依存するアプリや他のリソースが Microsoft Managed Desktop でスムーズに動作するために確認する必要がある内容について説明します。


## <a name="single-sign-on-for-on-premises-resources"></a>オンプレミス Sign-Onの単一のリソース

UPN Sign-Onを使用したシングル デバイス (SSO) は、Microsoft 管理デスクトップ デバイスで既定で有効になっています。 ただし、ユーザーは Windows Hello for Business を使用できます。追加のセットアップ手順が必要です。 

### <a name="single-sign-on-by-using-upn-and-password"></a>UPN Sign-Onパスワードを使用した単一のデバイス

ほとんどの組織では、ユーザーは MICROSOFT 管理デスクトップ デバイスで SSO を使用して UPN とパスワードによる認証を行えます。 ただし、この関数が動作する場合は、次の機能を確認してください。

- Azure AD Connect がセットアップされ、その後で実行されているオンプレミスの Active Directory サーバー Windows Server 2008 R2確認します。
- Azure AD Connect がサポートされているバージョンを実行し、これらの 3 つの属性を Azure サーバーと同期するようにAD。 
    - DNS ドメイン Active Directory の名前 (ユーザーが存在する場所)
    - オンプレミスの Active Directory の NetBIOS (ユーザーが存在する場所)
    - ユーザーの SAM アカウント名


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Windows Hello Sign-Onを使用した単一のアプリケーション

Microsoft Managed Desktop デバイスは、Windows Hello for Business を採用することで、ユーザーに高速でパスワードレスなエクスペリエンスを提供します。 ユーザーがそれぞれの UPN とパスワードを指定せずに Windows Hello for Business が動作するようにするには、「Azure AD に参加しているデバイスをオンプレミス用に構成する Single-Sign On using [Windows Hello for Business」](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) を参照して要件を確認し、そこに示す手順に従います。


## <a name="apps-and-resources-that-use-authentication"></a>認証を使用するアプリとリソース

Azure Active Directory [で動作するように](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) アプリを設定する方法の詳細については、「Azure コンテンツ セットのアプリケーションとリソースに関する考慮事項を理解する」を参照してください。 まとめると、以下のようになります。


- Azure ADアプリ ギャラリーに追加されたアプリなど、クラウドベースのアプリを使用する場合、Microsoft Managed Desktop を操作するためにそれ以上の準備は必要ない場合が多い。 ただし、Web アカウント マネージャー (WAM) を使用しない Win32 アプリでは、ユーザーに認証を求めるメッセージが表示される場合があります。

- オンプレミスでホストされている **アプリの場合は**、ブラウザーの信頼できるサイトの一覧にアプリを必ず追加してください。 この手順では、ユーザーに資格情報の入力を求めることなく、Windows 認証をシームレスに動作できます。 アプリを追加するには、「構成可能な設定 [」リファレンスの](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) 「信頼できる [サイト」を参照してください](../working-with-managed-desktop/config-setting-ref.md)。

- Active Directory フェデレーション サービスを使用している場合は、「FS でのシングル サインオンの確認と管理」の手順を使用して SSO が有効AD [します](/previous-versions/azure/azure-services/jj151809(v=azure.100))。 

- オンプレミス **で古い** プロトコルを使用するアプリの場合、デバイスが認証のためにオンプレミスのドメイン コントローラーにアクセスできる限り、追加のセットアップは必要ありません。 ただし、これらのアプリケーションにセキュリティで保護されたアクセスを提供するには、Azure ADアプリケーション プロキシを展開する必要があります。 詳細については、「Azure Active Directory のアプリケーション プロキシを介したオンプレミス アプリケーションへのリモート アクセス」 [を参照してください](/azure/active-directory/manage-apps/application-proxy)。

- オンプレミスで **実行され、** コンピューター認証に依存するアプリはサポートされていないので、新しいバージョンへの置き換えも検討する必要があります。

### <a name="network-shares-that-use-authentication"></a>認証を使用するネットワーク共有

UNC パスを使用してデバイスがオンプレミスのドメイン コントローラーにアクセスできる限り、ユーザーがネットワーク共有にアクセスするには、追加のセットアップは必要ありません。

### <a name="printers"></a>プリンター

ハイブリッド クラウド印刷を構成しない限り、Microsoft Managed Desktop デバイスは、オンプレミスの Active Directory に発行されたプリンター [に接続できません](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。

クラウド専用環境ではプリンターを自動的に検出することはできませんが、ユーザーは、デバイスがオンプレミスのドメイン コントローラーにアクセスできる限り、プリンター パスまたはプリンター キュー パスを使用してオンプレミスプリンターを使用できます。

<!--add fuller material on printers when available-->