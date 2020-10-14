---
title: 推奨されるセキュリティで保護されたドキュメントポリシー-Microsoft 365 for enterprise |Microsoft Docs
description: SharePoint ファイル アクセスをセキュリティで保護する方法に関する、Microsoft が推奨するポリシーについて説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: 653bd90fb68eb42423d5f32633736bba4b5943b4
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464314"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項

この記事では、SharePoint と OneDrive for business を保護するために推奨される id とデバイスアクセスポリシーを実装する方法について説明します。 このガイダンスは、 [共通の id およびデバイスアクセスポリシー](identity-access-policies.md)に基づいて構築されています。

これらの推奨事項は、ニーズの粒度 ( **基準**、 **機密**、 **高規制**) に基づいて適用できる、3つの異なるセキュリティと SharePoint ファイルの保護に基づいています。 これらのセキュリティ層および推奨されるクライアントオペレーティングシステムの詳細については、この推奨事項の [概要](microsoft-365-policies-configurations.md)を参照してください。

このガイダンスを実装するだけでなく、機密および規制の厳しいコンテンツに適切なアクセス許可を設定するなど、適切な保護を使用して SharePoint サイトを構成するようにしてください。

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>SharePoint および OneDrive for business を含めるための共通ポリシーの更新

SharePoint および OneDrive でファイルを保護するために、次の図は、共通 id およびデバイスアクセスポリシーから更新するポリシーを示しています。

[![Teams およびその依存サービスへのアクセスを保護するためのポリシー更新の概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

[この画像のより大きいバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

共通ポリシーを作成したときに SharePoint を含めた場合は、新しいポリシーを作成するだけで済みます。 条件付きアクセスポリシーの場合、SharePoint には OneDrive が含まれます。

新しいポリシーでは、指定した SharePoint サイトに特定のアクセス要件を適用することにより、機密および規制の厳しいコンテンツにデバイス保護を実装します。

次の表に、SharePoint の新しい内容を確認して更新または作成する必要があるポリシーを示します。 共通のポリシーは、 [一般的な id とデバイスアクセスポリシー](identity-access-policies.md) の記事に記載されている関連する構成手順にリンクしています。

|保護レベル|Policies|詳細|
|:---------------|:-------|:----------------|
|**Baseline**|[サインインリスクが*中*または*高*の場合は MFA を必須にする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウドアプリの割り当てに SharePoint を含める。|
|        |[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|クラウドアプリの割り当てに SharePoint を含める。|
|        |[アプリデータ保護ポリシーを適用する](identity-access-policies.md#apply-app-data-protection-policies)|アプリの一覧に推奨されるアプリがすべて含まれていることを確認してください。 各プラットフォーム (iOS、Android、Windows) のポリシーを更新してください。|
|        |[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|クラウドアプリの一覧に SharePoint を含める。|
|        |[SharePoint で適用されるアプリの制限を使用する](#use-app-enforced-restrictions-in-sharepoint)|この新しいポリシーを追加します。 これにより、SharePoint で指定された設定を使用するように Azure Active Directory (Azure AD) に通知されます。 このポリシーはすべてのユーザーに適用されますが、SharePoint アクセスポリシーに含まれるサイトへのアクセスにのみ影響します。|
|**機密**|[サインインリスクが*低*、*中*、*高*のときに MFA を必要とする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウドアプリの割り当てに SharePoint を含める。|
|         |[準拠 *して* いる pc とモバイルデバイスが必要](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|クラウドアプリの一覧に SharePoint を含める。|
||[Sharepoint アクセス制御ポリシー](#sharepoint-access-control-policies): 管理されていないデバイスから特定の SharePoint サイトへのアクセスをブラウザーのみに許可します。|これにより、ファイルの編集とダウンロードができなくなります。 PowerShell を使用してサイトを指定します。|
|**厳しく規制**|[*常に* MFA が必要](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウドアプリの割り当てに SharePoint を含める。|
||[Sharepoint アクセス制御ポリシー](#use-app-enforced-restrictions-in-sharepoint): 管理されていないデバイスから特定の SharePoint サイトへのアクセスをブロックします。|PowerShell を使用してサイトを指定します。|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>SharePoint でアプリに強制される制限を使用する

SharePoint でアクセス制御を実装する場合は、azure ad でこの条件付きアクセスポリシーを作成して、SharePoint で構成したポリシーを強制するように Azure ad に指示する必要があります。 このポリシーはすべてのユーザーに適用されますが、SharePoint でアクセス制御を作成するときに PowerShell を使用して指定したサイトへのアクセスにのみ影響します。

このポリシーを構成するには、[管理されていない [デバイスからのアクセスの制御](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)] の「特定の SharePoint サイトコレクションまたは OneDrive アカウントへのアクセスを禁止または制限する」を参照してください。

## <a name="sharepoint-access-control-policies"></a>SharePoint アクセス制御ポリシー

Microsoft では、デバイスアクセス制御を使用して、機密および規制の厳しいコンテンツを持つ SharePoint サイトのコンテンツを保護することをお勧めします。 これを行うには、保護レベルと保護を適用するサイトを指定するポリシーを作成します。

- 機密サイト: ブラウザーのみのアクセスを許可します。 これにより、ユーザーはファイルを編集してダウンロードすることができなくなります。
- 高度な規制サイト: 非管理対象デバイスからのアクセスをブロックします。

「管理されていない [デバイスからのアクセスを制御](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)する」の「特定の SharePoint サイトコレクションまたは OneDrive アカウントへのアクセスをブロックまたは制限する」を参照してください。

## <a name="how-these-policies-work-together"></a>これらのポリシーがどのように連携するか

SharePoint サイトのアクセス許可は、通常、サイトへのアクセスのビジネスニーズに基づくものであることを理解しておくことが重要です。 これらのアクセス許可はサイト所有者によって管理され、高度に動的にすることができます。 SharePoint デバイスアクセスポリシーを使用すると、ベースライン、機密、高度な規制保護に関連付けられた Azure AD グループにユーザーが割り当てられているかどうかにかかわらず、これらのサイトに対する保護が保証されます。

次の図は、SharePoint デバイスアクセスポリシーがユーザーのサイトへのアクセスを保護する方法の例を示しています。

[![サイトを保護する SharePoint デバイスアクセスポリシーの例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[この画像のより大きいバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

James には、ベースラインの条件付きアクセスポリシーが割り当てられていますが、機密または高度に規制された保護を使用して SharePoint サイトへのアクセス権を与えることができます。

- James が自分の PC を使用している、機密または高規制のサイトにアクセスすると、自分の PC が準拠している限り、そのアクセスが許可されます。
- James が、自分が管理されていない電話を使用して、自分のメンバーである機密サイトにアクセスすると、このサイトに対して構成されているデバイスアクセスポリシーにより、機密サイトへのブラウザーのみのアクセスが許可されます。
- James が管理されていない電話を使用して、自分のメンバーである、規制の厳しいサイトにアクセスすると、そのサイトに対して構成されたアクセスポリシーによってブロックされます。 このサイトにアクセスできるのは、管理対象の PC を使用している場合のみです。

## <a name="next-step"></a>次のステップ

![手順 4: Microsoft 365 クラウドアプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

次の条件付きアクセスポリシーを構成します。

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)

