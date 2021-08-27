---
title: マネージド セキュリティ サービス プロバイダー (MSSP) アクセスを提供する
description: ポータルからポータルへのMicrosoft Defender セキュリティ センターについてMicrosoft 365 Defenderする
keywords: Microsoft 365 Defender ポータル、microsoft Defender for Office 365、Microsoft Defender for Endpoint、MDO、MDE、単一ウィンドウのガラス、コンバージド ポータル、セキュリティ ポータル、Defender セキュリティ ポータルの開始
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
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
- m365initiative-m365-defender
ms.openlocfilehash: f5ef47fd03614c34e9cb459442e8c1f2a144f4b8
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58573885"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>マネージド セキュリティ サービス プロバイダー (MSSP) アクセスを提供する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**適用対象:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

マルチテナント委任アクセス ソリューションを実装するには、次の手順を実行します。

1. ポータル[で](/windows/security/threat-protection/microsoft-defender-atp/rbac)Defender for Endpoint で役割ベース Azure Active Directoryのアクセス制御を有効にし、Microsoft 365 Defender (Azure AD) グループに接続します。

2. アクセス [要求とプロビジョニング用にガバナンス](/azure/active-directory/governance/identity-governance-overview) アクセス パッケージを構成します。

3. Microsoft Myaccess でアクセス要求と監査 [を管理します](/azure/active-directory/governance/entitlement-management-request-approve)。

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-defender-portal"></a>Microsoft Defender for Endpoint で役割ベースのアクセス制御を有効にする (Microsoft 365 Defender ポータル)

1. **顧客 AAD で MSSP リソースのアクセス グループを作成する: グループ**

    これらのグループは、このポータルの Defender for Endpoint で作成したMicrosoft 365 Defenderされます。 これを行うには、テナントの顧客AD 3 つのグループを作成します。 この例のアプローチでは、次のグループを作成します。

    - Tier 1 Analyst
    - Tier 2 Analyst
    - MSSP アナリスト承認者  

2. ポータルの役割とグループ内の Customer Defender for Endpoint で適切なアクセス レベルに対応Microsoft 365 Defender Defender for Endpoint ロールを作成します。

    カスタマー Microsoft 365 Defender ポータルで RBAC を有効にするには、グローバル管理者またはセキュリティ管理者権限を持つユーザー アカウントを使用して、> **Endpoints** の役割 & グループ > Roles にアクセスします。

    ![MSSP アクセスのイメージ。](../../media/mssp-access.png)

    次に、MSSP SOC Tier のニーズを満たす RBAC ロールを作成します。 [割り当てられたユーザー グループ] を使用して、作成されたユーザー グループにこれらの役割をリンクします。

    2 つの可能な役割:

    - **Tier 1 Analysts** <br>
      ライブ応答以外のすべてのアクションを実行し、セキュリティ設定を管理します。

    - **Tier 2 Analysts** <br>
      ライブ応答に追加された Tier 1 [の機能](/windows/security/threat-protection/microsoft-defender-atp/live-response)

    詳細については、「役割ベースの [アクセス制御を使用する」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/rbac)。

## <a name="configure-governance-access-packages"></a>ガバナンス アクセス パッケージの構成

1. **顧客 AAD の接続組織として MSSP を追加する: ID ガバナンス**

    接続された組織として MSSP を追加すると、MSSP は要求し、アクセスが準備されます。 

    これを行うには、テナントの顧客AD、Identity Governance: Connected organization にアクセスします。 新しい組織を追加し、テナント ID またはドメインを使用して MSSP Analyst テナントを検索します。 MSSP Analysts 用に個別のADテナントを作成する方法をお勧めします。

2. **顧客 AAD でリソース カタログを作成する: ID ガバナンス**

    リソース カタログは、テナントの顧客に作成されたアクセス パッケージADです。

    これを行うには、テナントの顧客AD、Identity Governance: Catalogs にアクセスし、新しいカタログ **を追加します**。 この例では **、MSSP Accesses を呼び出します**。

    ![新しいカタログのイメージ。](../../media/goverance-catalog.png)

    詳細については、「リソースのカタログ [を作成する」を参照してください](/azure/active-directory/governance/entitlement-management-catalog-create)。

3. **MSSP リソースのアクセス パッケージを作成する 顧客 AAD: Identity Governance**

    アクセス パッケージは、承認時に要求者に付与される権限とアクセスのコレクションです。 

    これを行うには、テナントの顧客AD、Identity Governance: Access Package にアクセスし、新しいアクセス パッケージ **を追加します**。 MSSP 承認者と各アナリスト層のアクセス パッケージを作成します。 たとえば、次の Tier 1 Analyst 構成によって、次のようなアクセス パッケージが作成されます。

    - 新しい要求を承認するには、AD **MSSP アナリスト承認者** のメンバーが必要です。
    - SOC アナリストがアクセス拡張機能を要求できる年次アクセス レビューがある
    - MSSP SOC テナント内のユーザーだけが要求できる
    - 365 日後に自動アクセスが期限切れになる

    ![新しいアクセス パッケージのイメージ。](../../media/new-access-package.png)

    詳細については、「新しいアクセス [パッケージを作成する」を参照してください](/azure/active-directory/governance/entitlement-management-access-package-create)。

4. **顧客 AAD から MSSP リソースへのアクセス要求リンクを提供する: ID ガバナンス**

    [マイ アクセス ポータル] リンクは、MSSP SOC アナリストが作成したアクセス パッケージを介してアクセスを要求するために使用されます。 リンクは永続的です。つまり、同じリンクが新しいアナリストのために時間の間に使用される可能性があります。 アナリスト要求は、MSSP アナリスト承認者による承認のためにキュー **に入ります**。

    ![アクセス プロパティのイメージ。](../../media/access-properties.png)

    リンクは、各アクセス パッケージの概要ページに表示されます。

## <a name="manage-access"></a>アクセスを管理する

1. Customer または MSSP myaccess のアクセス要求を確認および承認します。

    アクセス要求は、MSSP Analyst Approvers グループのメンバーによって、お客様の My Access で管理されます。

    これを行うには、次を使用して顧客の myaccess にアクセスします `https://myaccess.microsoft.com/@<Customer Domain>` 。

    例: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`

2. UI の [承認] セクション **で要求を** 承認または拒否します。

     この時点でアナリスト アクセスが準備され、各アナリストは顧客のポータルにMicrosoft 365 Defenderがあります。

    `https://security.microsoft.com/?tid=<CustomerTenantId>` 割り当てられたアクセス許可とロールを使用します。

> [!IMPORTANT]
> Microsoft Defender for Endpoint への委任されたアクセスは、現在、Microsoft 365 Defenderウィンドウごとに 1 つのテナントにアクセスできます。
