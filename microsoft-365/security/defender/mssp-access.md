---
title: マネージド セキュリティ サービス プロバイダー (MSSP) へのアクセスを提供する
description: Microsoft Defender セキュリティ センターからMicrosoft 365 Defender ポータルへの変更について説明します
keywords: Microsoft 365 Defender ポータル、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、MDO、MDE、ガラスの単一ウィンドウ、コンバージド ポータル、セキュリティ ポータル、Defender セキュリティ ポータルの概要
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 3b3f438555be507d046f99838596a6672714e0ad
ms.sourcegitcommit: 6c2ab5e8efe74d0dc2df610e2d9d2fdda8aaf074
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65670226"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>マネージド セキュリティ サービス プロバイダー (MSSP) へのアクセスを提供する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**適用対象:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

マルチテナント委任アクセス ソリューションを実装するには、次の手順に従います。

1. Microsoft 365 Defender ポータルを使用して Defender for Endpoint の[ロールベースのアクセス制御](/microsoft-365/security/defender-endpoint/rbac)を有効にし、Azure Active Directory (Azure AD) グループに接続します。

2. Azure AD Identity Governance 内で [外部ユーザーのエンタイトルメント管理](/azure/active-directory/governance/entitlement-management-external-users) を構成して、アクセス要求とプロビジョニングを有効にします。

3. [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve) でアクセス要求と監査を管理します。

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでMicrosoft Defender for Endpointでロールベースのアクセス制御を有効にする

1. **Customer AAD: Groups で MSSP リソースのアクセス グループを作成する**

    これらのグループは、ポータルの Defender for Endpoint で作成したロールMicrosoft 365 Defenderリンクされます。 これを行うには、顧客 AD テナントで 3 つのグループを作成します。 このアプローチの例では、次のグループを作成します。

    - 階層 1 アナリスト
    - 階層 2 アナリスト
    - MSSP アナリスト承認者  

2. ポータルのロールとグループで、Customer Defender for Endpoint で適切なアクセス レベルの Defender for Endpoint ロールMicrosoft 365 Defender作成します。

    カスタマー Microsoft 365 Defender ポータルで RBAC を有効にするには、グローバル管理者またはセキュリティ管理者権限を持つユーザー アカウント **を使用して、アクセス許可>エンドポイント ロール&グループ>ロール** にアクセスします。

    :::image type="content" source="../../media/mssp-access.png" alt-text="Microsoft 365 Defender ポータルでの MSSP アクセスの詳細" lightbox="../../media/mssp-access.png":::

    次に、MSSP SOC 層のニーズを満たす RBAC ロールを作成します。 "割り当てられたユーザー グループ" を使用して、これらのロールを作成されたユーザー グループにリンクします。

    2 つの可能なロール:

    - **階層 1 アナリスト** <br>
      ライブ応答を除くすべてのアクションを実行し、セキュリティ設定を管理します。

    - **階層 2 アナリスト** <br>
      [ライブ応答](/microsoft-365/security/defender-endpoint/live-response)に追加された階層 1 の機能。

    詳細については、「 [ロールベースのアクセス制御を使用したポータル アクセスの管理](/microsoft-365/security/defender-endpoint/rbac)」を参照してください。

## <a name="configure-governance-access-packages"></a>ガバナンス アクセス パッケージを構成する

1. **顧客 AAD の接続された組織として MSSP を追加する: ID ガバナンス**

    接続された組織として MSSP を追加すると、MSSP は要求し、アクセスをプロビジョニングできます。 

    これを行うには、お客様の AD テナントで、Identity Governance: Connected organization にアクセスします。 新しい組織を追加し、テナント ID またはドメインを使用して MSSP アナリスト テナントを検索します。 MSSP アナリスト用に個別の AD テナントを作成することをお勧めします。

2. **Customer AAD: Identity Governance でリソース カタログを作成する**

    リソース カタログは、顧客 AD テナントで作成されたアクセス パッケージの論理コレクションです。

    これを行うには、顧客 AD テナントで Identity Governance: Catalogs にアクセスし、 **新しいカタログ** を追加します。 この例では、 **MSSP Accesses** と呼びます。

    :::image type="content" source="../../media/goverance-catalog.png" alt-text="Microsoft 365 Defender ポータルの新しいカタログ" lightbox="../../media/goverance-catalog.png":::


    詳細については、「 [リソースのカタログを作成する](/azure/active-directory/governance/entitlement-management-catalog-create)」を参照してください。

3. **MSSP リソースのアクセス パッケージを作成する 顧客 AAD: ID ガバナンス**

    アクセス パッケージは、承認時に要求元に付与される権限とアクセスのコレクションです。 

    これを行うには、お客様の AD テナントで、Identity Governance: Access Packages にアクセスし、 **新しいアクセス パッケージを追加します**。 MSSP 承認者と各アナリスト層のアクセス パッケージを作成します。 たとえば、次の階層 1 アナリスト構成では、次のようなアクセス パッケージが作成されます。

    - 新しい要求を承認するには、AD グループ **MSSP アナリスト承認者** のメンバーが必要です
    - SOC アナリストがアクセス拡張機能を要求できる年間アクセス レビューがあります。
    - MSSP SOC テナント内のユーザーのみが要求できます
    - アクセスの自動有効期限は 365 日後です

    :::image type="content" source="../../media/new-access-package.png" alt-text="Microsoft 365 Defender ポータルでの新しいアクセス パッケージの詳細" lightbox="../../media/new-access-package.png":::

    詳細については、「 [新しいアクセス パッケージの作成](/azure/active-directory/governance/entitlement-management-access-package-create)」を参照してください。

4. **顧客 AAD から MSSP リソースへのアクセス要求リンクを提供する: ID ガバナンス**

    My Access ポータル のリンクは、MSSP SOC アナリストが作成したアクセス パッケージを使用してアクセスを要求するために使用されます。 このリンクは持続性があり、新しいアナリストに対して同じリンクが時間の経過と共に使用される可能性があることを意味します。 アナリスト要求は、 **MSSP アナリスト承認者** による承認のためにキューに入ります。

    :::image type="content" source="../../media/access-properties.png" alt-text="Microsoft 365 Defender ポータルのアクセス プロパティ" lightbox="../../media/access-properties.png":::

    リンクは、各アクセス パッケージの概要ページにあります。

## <a name="manage-access"></a>アクセスを管理する

1. Customer または MSSP myaccess でアクセス要求を確認し、承認します。

    アクセス要求は、MSSP アナリスト承認者グループのメンバーによって、お客様の My Access で管理されます。

    これを行うには、次を使用して顧客の myaccess にアクセスします `https://myaccess.microsoft.com/@<Customer Domain>`。

    例: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`

2. UI の **承認** セクションで要求を承認または拒否します。

     この時点で、アナリストアクセスがプロビジョニングされ、各アナリストは顧客のMicrosoft 365 Defenderポータルにアクセスできる必要があります。

    `https://security.microsoft.com/?tid=<CustomerTenantId>` は、割り当てられたアクセス許可とロールを使用します。

> [!IMPORTANT]
> 現在、Microsoft 365 Defender ポータルでMicrosoft Defender for Endpointに委任されたアクセスでは、ブラウザー ウィンドウごとに 1 つのテナントにアクセスできます。
