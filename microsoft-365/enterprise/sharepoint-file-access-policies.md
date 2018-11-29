---
title: セキュリティで保護されたドキュメントの推奨されるポリシー - Microsoft 365 Enterprise | Microsoft Docs
description: SharePoint ファイル アクセスをセキュリティで保護する方法に関する、Microsoft が推奨するポリシーについて説明します。
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 2f5658146df3da7cc28c907b33e5035a84628fc5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869284"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項
この資料では、推奨されるユーザーと SharePoint Online とビジネスの OneDrive を保護するためにデバイスのアクセス ポリシーを実装する方法について説明します。このガイド[共通の id およびアクセス ポリシーをデバイス](identity-access-policies.md)に作成します。 


これらの推奨事項は、セキュリティの 3 つの異なる階層に基づいて、お客様のニーズの細分性に基づいて、適用可能な SharePoint ファイルの保護:**ベースライン**、**機密性の高い**、高度や**規制**対象とします。これらのセキュリティ層と、推奨されるクライアント オペレーティング システム、これらの推奨事項の[概要](microsoft-365-policies-configurations.md)を参照の詳細を学びます。

加えてこのガイダンスを実装するのには、必ず保護、規制の厳しいし、機密性の高いコンテンツは適切なアクセス許可の確認などの適切な量で SharePoint サイトを構成してください。ベースライン、機密性の高い、および規制の厳しい保護のためのサイトを作成する方法の詳細については、 [SharePoint のオンラインのセキュリティで保護されたサイトとファイル](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)を参照してください。 

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>SharePoint ビジネスの OneDrive など、共通のポリシーを更新します。
次の図は、ビジネスの SharePoint Online および OneDrive にあるファイルを保護するための推奨されるポリシーのセットを示しています。それは、どのポリシーが更新または SharePoint Online およびビジネスのための OneDrive の保護を追加するのには新しく作成されたことを示します。

![SharePoint Online および OneDrive のポリシーの概要](../images/identity-access-ruleset-sharepoint.png)

含まれている SharePoint Online 共通のポリシーを作成したとき場合、のみ、新しい polcies を作成する必要があります。条件付きのアクセス ルールを構成するには、SharePoint Online が含まれますビジネスの OneDrive には。

新しいポリシーでは、指定した SharePoint サイトに特定のアクセス要件を適用することで規制が厳しいし、機密性の高いコンテンツをデバイスの保護を実装します。 

 次の表は、ポリシーのいずれかを確認し、更新または SharePoint Online の新しいを作成する必要があります。共通のポリシーは、[共通の id とデバイスのアクセス ポリシー](identity-access-policies.md)の資料 (リンク準備中) に関連付けられている構成の手順をリンクします。


|保護レベル|[Policies]|詳細情報|
|:---------------|:-------|:----------------|
|**基準**|[サインインのリスクが*中*または*高*の場合は、MFA を必要とします。](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリケーションの割り当てには、SharePoint Online を含めます。|
|        |[現代の認証をサポートしていないクライアントをブロック](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|クラウド アプリケーションの割り当てには、SharePoint Online を含めます。|
|        |[アプリケーション保護のポリシーを定義します。](identity-access-policies.md#define-app-protection-policies)|推奨されるすべてのアプリケーションがアプリケーションの一覧に含まれていることを確認します。各プラットフォーム (iOS、Android、Windows) のポリシーを更新することを確認します。|
|        |[準拠の Pc を必要とします。](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|SharePoint Online クラウド アプリケーションの一覧に含まれます。|
|        |[使用アプリケーションは、SharePoint Online での制限を適用](#use-app-enforced-restrictions-in-sharepoint-online)|この新しいポリシーを追加します。これは、SharePoint Online で指定されている設定を使用する Azure AD を指示します。このルールは、すべてのユーザーに適用されますが、SharePoint Online のアクセス ポリシーに含まれているサイトへのアクセスにのみ影響します。
|**機密**|[サインインのリスクとは、*低*、*中*または*高*の場合は、MFA を必要とします。](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| クラウド アプリケーションの割り当てには、SharePoint Online を含めます。|
|         |[準拠の Pc*と*モバイル デバイスを必要とします。](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|SharePoint Online クラウド アプリケーションの一覧に含まれます。|
||[SharePoint Online のアクセス制御ポリシー](#sharepoint-online-access-control-policies): 管理されていないデバイスから特定の SharePoint サイトにブラウザー専用のアクセスを許可します。|これには、編集し、ファイルのダウンロードができなくなります。ユーザー PowerShell を使用して、サイトを指定します。|
|**高度な規制**|[*常に*requrie MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリケーションの割り当てには、SharePoint Online を含めます。 |
||[SharePoint Online のアクセス制御ポリシー](#use-app-enforced-restrictions-in-sharepoint-online): 特定の SharePoint サイトを管理されていないデバイスからのアクセスをブロック|PowerShell を使用すると、サイトを指定します。|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>使用アプリケーションは、SharePoint Online での制限を適用
SharePoint Online にアクセス制御を実装する場合は、SharePoint online を構成するポリシーを適用する Azure AD に指示する Azure AD でこの条件付きのアクセス ポリシーを作成する必要があります。このルールは、すべてのユーザーに適用されますが、SharePoint Online にアクセス制御を作成すると、PowerShell を使用して指定したサイトへのアクセスにのみ影響します。

この資料でこのポリシーを参照してください「特定の SharePoint サイト コレクション、または OneDrive のアカウントをブロックまたは制限アクセス」を構成するのには:[管理されていないデバイスからのアクセスを制御](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)します。


## <a name="sharepoint-online-access-control-policies"></a>SharePoint Online のアクセス制御ポリシー
デバイス アクセスの制御に機密性の高い、規制の厳しいのコンテンツを SharePoint サイトでコンテンツを保護することをお勧めします。これを行うとする保護を適用するサイトの保護のレベルを指定するポリシーを作成しています。 
- 機密性の高いサイト、ブラウザー専用のアクセスを許可します。これには、ユーザーを編集し、ファイルのダウンロードができなくなります。
- 規制の厳しいサイト-管理されていないデバイスからのアクセスをブロックします。

この資料の「特定の SharePoint サイト コレクション、または OneDrive アカウントをブロックまたは制限アクセス」を参照してください:[管理されていないデバイスからアクセス制御](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)をします。 

## <a name="how-these-policies-work-together"></a>これらのポリシーがどのように連携
SharePoint サイト アクセス許可レベルがサイトにアクセスするためのビジネスのニーズに基づく通常の理解に重要です。これらのアクセス許可は、サイトの所有者によって管理され、非常に動的にすることができます。デバイス アクセス ポリシーにより、ユーザーは Azure AD グループに割り当てられているかどうかに関係なく、これらのサイトを保護する SharePoint を使用して、機密性の高い基準に関連付けられているか、保護規制の厳しい。 

次の図は、デバイスのアクセス ポリシーの SharePoint サイトへのアクセスを保護する方法の例を提供します。

![SharePoint デバイスのアクセス ポリシーがサイトを保護する方法](../images/SharePoint-rules-scenario.png)

この図について:
- James は、基準計画の保護に関連する条件付きのアクセス ポリシーに割り当てられていますが、機密情報や規制の厳しい保護に関連付けられている SharePoint サイトに対するアクセス権を付与する彼ことができます。 
- ジェームズ、彼の自分の PC を使用してメンバーは、重要な情報や規制の厳しいサイトにアクセスするコンピューターが準拠している限り、アクセスが許可されます。
- James はアンマネージな電話は、基準計画のユーザーが許可されているを使用してのメンバーは、機密性の高いサイトにアクセスする場合はこのサイト用に構成されたデバイス アクセスのポリシーのための重要なサイトにブラウザー専用のアクセスを受け取ります。 
- James、アンマネージ電話を使用するメンバーは、規制の厳しいサイトにアクセスする場合はこのサイト用に構成されたアクセス ポリシーによりブロックされます。彼の管理と準拠の PC を使用してこのサイトにアクセスできるだけです。


<!---
##Block access to content from unmanaged devices (SharePoint admin center)
In the case of SharePoint Online, when a conditional access policy is applied to enforce Intune app protection policies, this might not apply to all applications that access SharePoint Online. Some applications, such as Exchange, have access to some SharePoint resources. For example, Exchange allows attaching SharePoint files by default. Conditional access policies applied to SharePoint Online will not restrict this access. 

To ensure baseline protection is applied uniformly, regardless of which service is accessing SharePoint Online and OneDrive for Business, configure access controls directly in SharePoint admin center. We recommend you configure the following:
- Block access from unmanaged devices. This includes devices that aren't compliant or joined to a domain. 
- Block access from app that don't use modern authentication.

See [Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).
-->



## <a name="next-steps"></a>次の手順
[SharePoint Online サイトとファイルをセキュリティで保護する](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
