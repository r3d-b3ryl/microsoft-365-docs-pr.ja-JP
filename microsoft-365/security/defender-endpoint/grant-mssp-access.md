---
title: マネージド セキュリティ サービス プロバイダー (MSSP) へのアクセスを許可する
description: MSSP と Microsoft Defender for Endpointの統合を構成するために必要な手順を実行します。
keywords: マネージド セキュリティ サービス プロバイダー、mssp、構成、統合
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c8a96f3dba51de09a7237279b4053b9f4ed9b4a7
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470485"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a>マネージド セキュリティ サービス プロバイダー (MSSP) へのアクセスを許可する (プレビュー)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

マルチテナント委任アクセス ソリューションを実装するには、次の手順に従います。

1. Defender for Endpoint で [ロールベースのアクセス制御](rbac.md) を有効にし、Active Directory (AD) グループに接続します。

2. アクセス要求とプロビジョニングのために [ガバナンス アクセス パッケージ](/azure/active-directory/governance/identity-governance-overview) を構成します。

3. [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve) でアクセス要求と監査を管理します。

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointでロールベースのアクセス制御を有効にする

1. **カスタマー AAD: グループで MSSP リソースのアクセス グループを作成する**

    これらのグループは、Defender for Endpoint で作成したロールにリンクされます。 これを行うには、顧客 AD テナントで 3 つのグループを作成します。 このアプローチの例では、次のグループを作成します。

    - 階層 1 アナリスト
    - 階層 2 アナリスト
    - MSSP アナリスト承認者

2. Customer Defender for Endpoint で適切なアクセス レベルの Defender for Endpoint ロールを作成します。

    カスタマー Microsoft 365 Defender ポータルで RBAC を有効にするには、グローバル管理者またはセキュリティ管理者権限を持つユーザー アカウントから、**設定 >アクセス許可>ロール** と "ロールを有効にする" にアクセスします。

    :::image type="content" source="images/mssp-access.png" alt-text="MSSP アクセス" lightbox="images/mssp-access.png":::

    次に、MSSP SOC 層のニーズを満たす RBAC ロールを作成します。 "割り当てられたユーザー グループ" を使用して、これらのロールを作成されたユーザー グループにリンクします。

    2 つの可能なロール:

    - **階層 1 アナリスト**

      ライブ応答を除くすべてのアクションを実行し、セキュリティ設定を管理します。

    - **階層 2 アナリスト**

      [ライブ応答](live-response.md)に追加された階層 1 の機能

    詳細については、「 [ロールベースのアクセス制御を使用する](rbac.md)」を参照してください。

## <a name="configure-governance-access-packages"></a>ガバナンス アクセス パッケージを構成する

1. **顧客AADで接続された組織として MSSP を追加する: ID ガバナンス**

    接続された組織として MSSP を追加すると、MSSP は要求し、アクセスをプロビジョニングできます。

    これを行うには、お客様の AD テナントで、Identity Governance: Connected organization にアクセスします。 新しい組織を追加し、テナント ID またはドメインを使用して MSSP アナリスト テナントを検索します。 MSSP アナリスト用に個別の AD テナントを作成することをお勧めします。

2. **Customer AAD: Identity Governance でリソース カタログを作成する**

    リソース カタログは、顧客 AD テナントで作成されたアクセス パッケージの論理コレクションです。

    これを行うには、顧客 AD テナントで Identity Governance: Catalogs にアクセスし、 **新しいカタログ** を追加します。 この例では、 **MSSP Accesses** と呼びます。

    :::image type="content" source="images/goverance-catalog.png" alt-text="新しいカタログ ページ" lightbox="images/goverance-catalog.png":::

    詳細については、「 [リソースのカタログを作成する](/azure/active-directory/governance/entitlement-management-catalog-create)」を参照してください。

3. **MSSP リソースのアクセス パッケージを作成する カスタマー AAD: Identity Governance**

    アクセス パッケージは、承認時に要求元に付与される権限とアクセスのコレクションです。

    これを行うには、お客様の AD テナントで、Identity Governance: Access Packages にアクセスし、 **新しいアクセス パッケージを追加します**。 MSSP 承認者と各アナリスト層のアクセス パッケージを作成します。 たとえば、次の階層 1 アナリスト構成では、次のようなアクセス パッケージが作成されます。

    - 新しい要求を承認するには、AD グループ **MSSP アナリスト承認者** のメンバーが必要です
    - SOC アナリストがアクセス拡張機能を要求できる年間アクセス レビューがあります。
    - MSSP SOC テナント内のユーザーのみが要求できます
    - アクセスの自動有効期限は 365 日後です

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/new-access-package.png" alt-text="[新しいアクセス パッケージ] ページ" lightbox="images/new-access-package.png":::

    詳細については、「 [新しいアクセス パッケージの作成](/azure/active-directory/governance/entitlement-management-access-package-create)」を参照してください。

4. **カスタマー AAD: Identity Governance から MSSP リソースへのアクセス要求リンクを提供する**

    My Access ポータル のリンクは、MSSP SOC アナリストが作成したアクセス パッケージを使用してアクセスを要求するために使用されます。 このリンクは持続性があり、新しいアナリストに対して同じリンクが時間の経過と共に使用される可能性があることを意味します。 アナリスト要求は、 **MSSP アナリスト承認者** による承認のためにキューに入ります。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/access-properties.png" alt-text="[プロパティ] ページ" lightbox="images/access-properties.png":::

    リンクは、各アクセス パッケージの概要ページにあります。

## <a name="manage-access"></a>アクセスを管理する

1. Customer または MSSP myaccess でアクセス要求を確認し、承認します。

    アクセス要求は、MSSP アナリスト承認者グループのメンバーによって、お客様の My Access で管理されます。

    これを行うには、次を使用して顧客の myaccess にアクセスします `https://myaccess.microsoft.com/@<Customer Domain>`。

    例: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`

2. UI の **承認** セクションで要求を承認または拒否します。

    この時点で、アナリストアクセスがプロビジョニングされ、各アナリストは顧客のMicrosoft 365 Defenderポータルにアクセスできる必要があります。`https://security.microsoft.com/?tid=<CustomerTenantId>`

## <a name="related-topics"></a>関連項目

- [MSSP カスタマー ポータルにアクセスする](access-mssp-portal.md)
- [アラート通知を構成する](configure-mssp-notifications.md)
- [顧客テナントからアラートを取得する](fetch-alerts-mssp.md)
