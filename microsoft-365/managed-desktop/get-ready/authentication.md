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
audience: Admin
ms.openlocfilehash: ffe432df946844b2ac06b87c2c5ca4284d49e0a1
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59163806"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する

このMicrosoft マネージド デスクトップデバイスは自動的に (Azure Azure Active Directory) AD。 このため、オンプレミスの Active Directory を使用している場合は、Azure AD に参加しているデバイスがオンプレミスの Active Directory と通信できるよう、いくつかのことを確認する必要があります。 

> [!NOTE]  
> *ハイブリッド* Azure AD参加は、ユーザーがサポートMicrosoft マネージド デスクトップ。

Azure Active Directoryを使用すると、ユーザーはシングル Sign-On (SSO) を利用できます。つまり、通常、ユーザーはリソースを使用する度に資格情報を提供する必要がなされます。

参加方法の詳細[Azure Active Directory、「How to: Plan your Azure AD実装」を参照してください](/azure/active-directory/devices/azureadjoin-plan)。 Azure AD に参加しているデバイスでのシングル Sign-On (SSO) のバックグラウンド情報については [、「Azure](/azure/active-directory/devices/azuread-join-sso#how-it-works)AD 参加デバイスでのオンプレミス リソースへの SSO の動作」を参照してください。


この記事では、ローカルの Active Directory 接続に依存するアプリや他のリソースが、ローカル Active Directory 接続でスムーズに動作するために確認する必要があるMicrosoft マネージド デスクトップ。


## <a name="single-sign-on-for-on-premises-resources"></a>オンプレミス Sign-Onの単一のリソース

UPN Sign-Onを使用したシングル Sign-On (SSO) は、デバイスで既定でMicrosoft マネージド デスクトップされます。 ただし、ユーザーはビジネス向けWindows Helloを使用できますが、追加のセットアップ手順が必要です。 

### <a name="single-sign-on-by-using-upn-and-password"></a>UPN Sign-Onパスワードを使用した単一のデバイス

ほとんどの組織では、ユーザーは SSO を使用して、デバイス上の UPN とパスワードMicrosoft マネージド デスクトップできます。 ただし、この関数が動作する場合は、次の機能を確認してください。

- Azure AD Connectがセットアップされ、サーバー 2008 R2 以降で実行されているオンプレミスの Active Directory サーバー Windows使用します。
- Azure AD Connectがサポートされているバージョンを実行し、これらの 3 つの属性を Azure サーバーと同期するようにAD。 
    - DNS ドメイン Active Directory の名前 (ユーザーが存在する場所)
    - オンプレミスの Active Directory の NetBIOS (ユーザーが存在する場所)
    - ユーザーの SAM アカウント名


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>ビジネスSign-Onを使用した単一Windows Helloサービス

Microsoft マネージド デスクトップデバイスは、ビジネス向けアプリを採用することで、ユーザーに迅速でパスワードレスWindows Hello提供します。 ユーザーがそれぞれの UPN とパスワードを指定せずに Windows Hello for Business が動作するようにするには、「Azure AD に参加しているデバイスをオンプレミス用に構成する Single-Sign On using [Windows Hello for Business」](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)を参照して要件を確認し、そこに示されている手順に従います。


## <a name="apps-and-resources-that-use-authentication"></a>認証を使用するアプリとリソース

詳細については[、「Azure コンテンツ セット内](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources)のアプリケーションとリソースに関する考慮事項を理解する」を参照して、アプリケーションを使用して動作するようにアプリを設定Azure Active Directory。 まとめると、以下のようになります。


- Azure ADアプリ ギャラリーに追加されたアプリなど、クラウドベースのアプリを使用する場合、ほとんどの場合、Microsoft マネージド デスクトップ を操作するためにそれ以上の準備は必要Microsoft マネージド デスクトップ。 ただし、Web アカウント マネージャー (WAM) を使用しない Win32 アプリでは、ユーザーに認証を求めるメッセージが表示される場合があります。

- オンプレミスでホストされている **アプリの場合は**、ブラウザーの信頼できるサイトの一覧にアプリを必ず追加してください。 この手順では、ユーザー Windows求めることなく、認証をシームレスに動作できます。 アプリを追加するには、「構成可能な設定 [」リファレンスの](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) 「信頼できる [サイト」を参照してください](../working-with-managed-desktop/config-setting-ref.md)。

- Active Directory フェデレーション サービスを使用している場合は、「FS でのシングル サインオンの確認と管理」の手順を使用して SSO が有効AD [します](/previous-versions/azure/azure-services/jj151809(v=azure.100))。 

- オンプレミス **で古い** プロトコルを使用するアプリの場合、デバイスが認証のためにオンプレミスのドメイン コントローラーにアクセスできる限り、追加のセットアップは必要ありません。 ただし、これらのアプリケーションにセキュリティで保護されたアクセスを提供するには、Azure ADアプリケーション プロキシを展開する必要があります。 詳細については、「アプリケーション プロキシを介したオンプレミス アプリケーションへのリモート アクセス[Azure Active Directoryを参照してください](/azure/active-directory/manage-apps/application-proxy)。

- オンプレミスで **実行され、** コンピューター認証に依存するアプリはサポートされていないので、新しいバージョンへの置き換えも検討する必要があります。

### <a name="network-shares-that-use-authentication"></a>認証を使用するネットワーク共有

UNC パスを使用してデバイスがオンプレミスのドメイン コントローラーにアクセスできる限り、ユーザーがネットワーク共有にアクセスするには、追加のセットアップは必要ありません。

### <a name="printers"></a>プリンター

Microsoft マネージド デスクトップハイブリッド クラウド印刷を構成しない限り、オンプレミスの Active Directory に発行されたプリンターにデバイス[を接続できません](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。

クラウド専用環境ではプリンターを自動的に検出することはできませんが、ユーザーは、デバイスがオンプレミスのドメイン コントローラーにアクセスできる限り、プリンター パスまたはプリンター キュー パスを使用してオンプレミスプリンターを使用できます。

<!--add fuller material on printers when available-->
## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>インストールの準備を行うMicrosoft マネージド デスクトップ

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
2. [準備状況の評価ツール](readiness-assessment-tool.md)を実行します。
1. [ポータル サイト](../get-started/company-portal.md)を購入します。
1. [ゲスト アカウントの前提条件](guest-accounts.md)を確認します。
1. [ネットワーク構成](network.md)をチェックします。
1. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
1. データへのユーザー アクセスを準備します (この記事)。
1. [アプリを準備します](apps.md)。
1. [マップ済みドライブを準備します](mapped-drives.md)。
1. [印刷リソースを準備します](printing.md)。
1. [デバイス名](address-device-names.md)をアドレス指定します。