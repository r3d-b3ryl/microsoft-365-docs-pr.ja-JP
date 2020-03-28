---
title: セキュリティで保護されたドキュメントの推奨されるポリシー - Microsoft 365 Enterprise | Microsoft Docs
description: SharePoint ファイル アクセスをセキュリティで保護する方法に関する、Microsoft が推奨するポリシーについて説明します。
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 2b0d015485196bc76e7de580c888892967fe5d05
ms.sourcegitcommit: c079cc893cd1bd5d894b13814063a2f42238806e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43035125"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項

この記事では、SharePoint Online と OneDrive for business を保護するために推奨される id とデバイスアクセスポリシーを実装する方法について説明します。 このガイダンスは、[共通の id およびデバイスアクセスポリシー](identity-access-policies.md)に基づいて構築されています。

これらの推奨事項は、ニーズの粒度 (**基準**、**機密**、**高規制**) に基づいて適用できる、3つの異なるセキュリティと SharePoint ファイルの保護に基づいています。 これらのセキュリティ層および推奨されるクライアントオペレーティングシステムの詳細については、この推奨事項の[概要](microsoft-365-policies-configurations.md)を参照してください。

このガイダンスを実装するだけでなく、機密および規制の厳しいコンテンツに適切なアクセス許可を設定するなど、適切な保護を使用して SharePoint サイトを構成するようにしてください。 ベースライン、機密、および高度な規制保護用のサイトを作成する方法の詳細については、「 [Secure SharePoint Online sites and files](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)」を参照してください。

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>SharePoint および OneDrive for business を含めるための共通ポリシーの更新

次の図は、SharePoint Online と OneDrive for business のファイルを保護するために推奨されるポリシーのセットを示しています。 この値は、SharePoint Online と OneDrive for business の保護を追加するために、どのポリシーを更新または新規作成する必要があるかを示します。

![SharePoint Online および OneDrive のポリシーの概要](../media/identity-access-ruleset-sharepoint.png)

共通ポリシーの作成時に SharePoint Online を含めた場合は、新しいポリシーを作成するだけで済みます。 条件付きアクセスルールを構成する場合は、SharePoint Online に OneDrive for Business が含まれています。

新しいポリシーでは、指定した SharePoint サイトに特定のアクセス要件を適用することにより、機密および規制の厳しいコンテンツにデバイス保護を実装します。

次の表に、SharePoint Online の新しい内容を確認し、更新または作成する必要があるポリシーを示します。 共通のポリシーは、[一般的な id とデバイスアクセスポリシー](identity-access-policies.md)の記事に記載されている関連する構成手順にリンクしています。

|保護レベル|ポリシー|詳細情報|
|:---------------|:-------|:----------------|
|**Baseline**|[サインインリスクが*中*または*高*の場合は MFA を必須にする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウドアプリの割り当てに SharePoint Online を含める|
|        |[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|クラウドアプリの割り当てに SharePoint Online を含める|
|        |[アプリデータ保護ポリシーを適用する](identity-access-policies.md#apply-app-data-protection-policies)|アプリの一覧に推奨されるアプリがすべて含まれていることを確認してください。 各プラットフォーム (iOS、Android、Windows) のポリシーを更新してください。|
|        |[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|クラウドアプリの一覧に SharePoint Online を含める|
|        |[SharePoint Online で適用されるアプリの制限を使用する](#use-app-enforced-restrictions-in-sharepoint-online)|この新しいポリシーを追加します。 これにより、Azure AD は、SharePoint Online で指定された設定を使用するように指示されます。 このルールはすべてのユーザーに適用されますが、SharePoint Online アクセスポリシーに含まれるサイトへのアクセスのみに影響します。|
|**機密**|[サインインリスクが*低*、*中*、*高*のときに MFA を必要とする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウドアプリの割り当てに SharePoint Online を含める|
|         |[準拠*して*いる pc とモバイルデバイスが必要](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|クラウドアプリの一覧に SharePoint Online を含める|
||[Sharepoint Online のアクセス制御ポリシー](#sharepoint-online-access-control-policies): 管理されていないデバイスからの特定の SharePoint サイトへのブラウザー専用アクセスを許可する|これにより、ファイルの編集とダウンロードができなくなります。 PowerShell を使用してサイトを指定する|
|**高度な規制**|[*常に*MFA が必要](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウドアプリの割り当てに SharePoint Online を含める|
||[Sharepoint Online のアクセス制御ポリシー](#use-app-enforced-restrictions-in-sharepoint-online): 管理されていないデバイスから特定の SharePoint サイトへのアクセスをブロックする|PowerShell を使用してサイトを指定する|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>SharePoint Online でアプリに強制される制限を使用する

SharePoint Online でアクセス制御を実装する場合は、azure ad でこの条件付きアクセスポリシーを作成して、SharePoint Online で構成したポリシーを適用するように Azure AD に指示する必要があります。 このルールはすべてのユーザーに適用されますが、SharePoint Online でアクセス制御を作成するときに PowerShell を使用して指定したサイトへのアクセスにのみ影響します。

このポリシーを構成するには、この記事の「管理されていない[デバイスからのアクセスを制御](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)する」の「特定の SharePoint サイトコレクションまたは OneDrive アカウントへのアクセスを禁止または制限する」を参照してください。

## <a name="sharepoint-online-access-control-policies"></a>SharePoint Online のアクセス制御ポリシー

Microsoft では、デバイスアクセス制御を使用して、機密および規制の厳しいコンテンツを持つ SharePoint サイトのコンテンツを保護することをお勧めします。 これを行うには、保護レベルと保護を適用するサイトを指定するポリシーを作成します。

- 機密サイト: ブラウザーのみのアクセスを許可します。 これにより、ユーザーはファイルを編集してダウンロードすることができなくなります。
- 高度な規制サイト: 非管理対象デバイスからのアクセスをブロックします。

この記事の「管理されていない[デバイスからのアクセスを制御](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)する」の「特定の SharePoint サイトコレクションまたは OneDrive アカウントへのアクセスをブロックまたは制限する」を参照してください。

## <a name="how-these-policies-work-together"></a>これらのポリシーがどのように連携するか

SharePoint サイトのアクセス許可は、通常、サイトへのアクセスのビジネスニーズに基づくものであることを理解しておくことが重要です。 これらのアクセス許可はサイト所有者によって管理され、高度に動的にすることができます。 SharePoint デバイスアクセスポリシーを使用すると、ベースライン、機密、高度な規制保護に関連付けられた Azure AD グループにユーザーが割り当てられているかどうかにかかわらず、これらのサイトに対する保護が保証されます。

次の図は、SharePoint デバイスアクセスポリシーがサイトへのアクセスを保護する方法の例を示しています。

![SharePoint デバイスアクセスポリシーがサイトを保護する方法](../media/SharePoint-rules-scenario.png)

この図について:

- James は、ベースライン保護に関連付けられている条件付きアクセスポリシーに割り当てられますが、機密または高規制の保護に関連付けられた SharePoint サイトへのアクセス権を付与することができます。
- James が自分の PC を使用している、機密または高規制のサイトにアクセスすると、自分の PC が準拠している限り、そのアクセスが許可されます。
- James が、自分が管理されていない電話を使用して、自分のメンバーである機密サイトにアクセスすると、このサイトに対して構成されているデバイスアクセスポリシーにより、機密サイトへのブラウザーのみのアクセスが許可されます。
- James が管理されていない電話を使用して、自分のメンバーである、規制の厳しいサイトにアクセスすると、そのサイトに対して構成されたアクセスポリシーによってブロックされます。 このサイトにアクセスできるのは、管理対象の PC を使用している場合のみです。

## <a name="next-steps"></a>次の手順

[SharePoint Online サイトとファイルをセキュリティで保護する](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
