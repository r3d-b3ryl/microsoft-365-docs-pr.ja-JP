---
title: Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する
description: 認証を提供するために Azure ADオンプレミスの組織と通信AD確認するための重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c1732dc17188427f9a181d1c47abe71bb8f39584
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841413"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する

Microsoft マネージド デスクトップでは、デバイスは自動的に Azure Active Directory (Azure AD) に参加します。 このため、オンプレミスの Active Directory を使用している場合は、Azure AD に参加しているデバイスがオンプレミスの Active Directory と通信できるよう、いくつかのことを確認する必要があります。 

> [!NOTE]  
> *ハイブリッド* Azure AD参加は、Microsoft マネージド デスクトップではサポートされていません。

Azure Active Directory を使用すると、ユーザーはシングル Sign-On (SSO) を利用できます。つまり、通常、ユーザーはリソースを使用する度に資格情報を提供する必要がなされません。

Azure Active Directory への参加の詳細については、「方法: Azure active Directory への参加の実装AD [参照してください](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)。 Azure AD に参加しているデバイスでのシングル Sign-On (SSO) の背景情報については [、「Azure](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)AD に参加しているデバイスでのオンプレミス リソースへの SSO の動作」を参照してください。


この記事では、ローカルの Active Directory 接続に依存するアプリや他のリソースが Microsoft マネージド デスクトップで円滑に動作するために確認する必要がある項目について説明します。


## <a name="single-sign-on-for-on-premises-resources"></a>オンプレミス Sign-On単一のリソース

MICROSOFT Sign-On デバイスでは、UPN とパスワードを使用したシングル クライアント (SSO) が既定で有効になっています。 ただし、ユーザーは Windows Hello for Business も使用できます。追加のセットアップ手順が必要です。 

### <a name="single-sign-on-by-using-upn-and-password"></a>UPN Sign-Onパスワードを使用した単一の構成

ほとんどの組織では、ユーザーは MICROSOFT マネージド デスクトップ デバイスで SSO を使用して UPN とパスワードで認証できます。 ただし、この関数が動作するには、次のことを確認する必要があります。

- Azure AD Connect がセットアップされ、その後で実行されているオンプレミスの Active Directory サーバー Windows Server 2008 R2確認します。
- Azure AD Connect がサポートされているバージョンを実行し、これら 3 つの属性を Azure AD と同期するように設定AD。 
    - DNS ドメイン Active Directory の名前 (ユーザーが存在する場所)
    - オンプレミスの Active Directory の NetBIOS (ユーザーが存在する場所)
    - ユーザーの SAM アカウント名


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Windows Hello for Business Sign-On使用した単一の機能

また、Microsoft マネージド デスクトップ デバイスでは、Windows Hello for Business を使用して、ユーザーに高速でパスワードレスなエクスペリエンスを提供します。 ユーザーがそれぞれの UPN とパスワードを入力せずに Windows Hello for Business が動作するようにするには、「Azure AD に参加しているデバイスをオンプレミスの Single-Sign 用に構成する」にアクセスして [、Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) を使用して要件を確認し、そこで提供されている手順に従ってください。


## <a name="apps-and-resources-that-use-authentication"></a>認証を使用するアプリとリソース

Azure Active Directory [で動作する](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) アプリの設定に関する完全なガイダンスについては、Azure コンテンツ セットのアプリケーションとリソースに関する考慮事項を理解するを参照してください。 まとめると、以下のようになります。


- Azure ADアプリ ギャラリーに追加されたアプリなど、クラウドベースのアプリを使用する場合、Microsoft マネージド デスクトップで動作するためにそれ以上の準備は必要ない場合があります。 ただし、Web アカウント マネージャー (WAM) を使用しない Win32 アプリでは、ユーザーに認証を求めるメッセージが表示される場合があります。

- オンプレミスでホスト **されているアプリの** 場合は、ブラウザーの信頼済みサイト一覧にそれらのアプリを追加してください。 この手順を実行すると、ユーザーに資格情報の入力を求めることなく、Windows 認証をシームレスに動作できます。 アプリを追加するには、構成可能な設定 [のリファレンスの](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) 「信頼済み [サイト」を参照してください](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)。

- Active Directory フェデレーション サービスを使用している場合は、「AD FS を使用してシングル サインオンを確認および管理する」の手順に従って [SSO が有効ADします](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))。 

- オンプレミス **で古い** プロトコルを使用するアプリの場合、デバイスが認証のためにオンプレミスのドメイン コントローラーにアクセスできる限り、追加のセットアップは必要ありません。 ただし、これらのアプリケーションに安全なアクセスを提供するには、Azure AD Application Proxy を展開する必要があります。 詳細については、Azure Active Directory のアプリケーション プロキシを介したオンプレミス アプリケーションへのリモート アクセス [に関するページを参照してください](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)。

- オンプレミスで **実行され** 、コンピューター認証に依存するアプリはサポートされていないので、新しいバージョンに置き換える必要があります。

### <a name="network-shares-that-use-authentication"></a>認証を使用するネットワーク共有

UNC パスを使用してデバイスがオンプレミスのドメイン コントローラーにアクセスできる限り、ユーザーがネットワーク共有にアクセスするために追加のセットアップは必要ありません。

### <a name="printers"></a>プリンター

Microsoft マネージド デスクトップ デバイスは、ハイブリッド クラウド印刷を構成しない限り、オンプレミスの Active Directory に発行されたプリンター [に接続できません](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。

クラウド専用環境でプリンターを自動的に検出することはできませんが、ユーザーは、デバイスがオンプレミスのドメイン コントローラーにアクセスできる限り、プリンター パスまたはプリンター キュー パスを使用してオンプレミスのプリンターを使用できます。

<!--add fuller material on printers when available-->
