---
title: Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender
description: Microsoft Defender セキュリティ センターから Microsoft 365 セキュリティ センターへの変更点について説明します。
keywords: Microsoft 365 セキュリティ センター、OATP、MDATP、MDO、MDE、単一ウィンドウ、統合ポータル、セキュリティ ポータル、Defender セキュリティ ポータルの使用を開始する
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
- m365initiative-m365-defender
ms.openlocfilehash: 96d5a3bdbd0acbf428f01cc3bb5afefaa95950b4
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242965"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>マネージ セキュリティ サービス プロバイダー (MSSP) アクセスを提供する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

マルチテナントの委任アクセス ソリューションを実装するには、次の手順を実行します。

1. Microsoft [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) 365 セキュリティ センターのエンドポイント用 Defender で役割ベースのアクセス制御を有効にし、Azure Active Directory (Azure AD) グループに接続します。

2. アクセス [要求とプロビジョニング用にガバナンス](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) アクセス パッケージを構成します。

3. Microsoft Myaccess でアクセス要求と監査 [を管理します](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve)。

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender で役割ベースのアクセス制御を有効にする

1. **顧客 AAD で MSSP リソースのアクセス グループを作成する: グループ**

    これらのグループは、Microsoft 365 セキュリティ センターの Defender for Endpoint で作成した役割にリンクされます。 これを行うには、テナントの顧客AD 3 つのグループを作成します。 この例のアプローチでは、次のグループを作成します。

    - 第 1 層アナリスト 
    - 第 2 層アナリスト 
    - MSSP アナリスト承認者  


2. Microsoft 365 セキュリティ センターの役割とグループの Customer Defender for Endpoint で、適切なアクセス レベルに対応したエンドポイント用 Defender の役割を作成します。

    お客様の Microsoft 365 セキュリティ センターで RBAC を有効にするには、グローバル管理者またはセキュリティ管理者の権限を持つユーザー アカウントを使用して、アクセス許可 > エンドポイントの役割 & グループ **> の** 役割にアクセスします。

    ![MSSP アクセスの画像](../../media/mssp-access.png)

    次に、MSSP SOC 層のニーズを満たす RBAC の役割を作成します。 "割り当てられたユーザー グループ" を使用して、作成されたユーザー グループにこれらの役割をリンクします。

    次の 2 つの役割を使用できます。

    - **第 1 層アナリスト** <br>
      ライブ応答以外のすべてのアクションを実行し、セキュリティ設定を管理します。

    - **第 2 層アナリスト** <br>
      ライブ応答に追加された階層 1 [の機能](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)

    詳細については、「役割ベースの [アクセス制御を使用する」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)。



## <a name="configure-governance-access-packages"></a>ガバナンス アクセス パッケージを構成する

1.  **顧客 AAD で接続された組織として MSSP を追加する: ID ガバナンス**
    
    接続された組織として MSSP を追加すると、MSSP が要求し、アクセスが準備されます。 

    これを行うには、テナントの顧客AD、Identity Governance: Connected organization にアクセスします。 新しい組織を追加し、テナント ID またはドメインを使用して MSSP アナリストのテナントを検索します。 MSSP アナリスト用にADテナントを作成してください。

2. **顧客 AAD でリソース カタログを作成する: ID ガバナンス**

    リソース カタログはアクセス パッケージの論理コレクションで、テナントの顧客ADされます。

    これを行うには、顧客管理テナントでADガバナンス: カタログにアクセスし、新しいカタログ **を追加します**。 この例では **、MSSP Accesses と呼び出します**。 

    ![新しいカタログの画像](../../media/goverance-catalog.png)

    詳細については、「リソースのカタログ [を作成する」を参照してください](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)。


3. **MSSP リソース Customer AAD: Identity Governance 用のアクセス パッケージを作成する**

    アクセス パッケージは、承認時に要求者に付与される権限とアクセスのコレクションです。 

    これを行うには、顧客管理テナントでADガバナンス: アクセス パッケージにアクセスし、新しいアクセス パッケージ **を追加します**。 MSSP 承認者と各アナリスト層のアクセス パッケージを作成します。 たとえば、次の階層 1 アナリストの構成では、次のようなアクセス パッケージが作成されます。

    - 新しい要求を承認するにはAD **MSSP アナリスト承認者** グループのメンバーが必要です。
    - SOC アナリストがアクセスの延長を要求できる年次アクセス レビューがある
    - MSSP SOC テナント内のユーザーだけが要求できます
    - Access auto expires after 365 days

    ![新しいアクセス パッケージの画像](../../media/new-access-package.png)

    詳細については、「新しいアクセス パッケージ [を作成する」を参照してください](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)。


4. **顧客 AAD から MSSP リソースへのアクセス要求リンクを提供する: ID ガバナンス**

    マイ アクセス ポータルリンクは、MSSP SOC アナリストが作成したアクセス パッケージを介したアクセスを要求するために使用されます。 リンクは永続的です。つまり、新しいアナリストにも同じリンクが使用される可能性があります。 アナリストの要求は、MSSP アナリスト承認者による承認を得 **るキューに入ります**。


    ![アクセス プロパティの画像](../../media/access-properties.png)

    リンクは、各アクセス パッケージの概要ページに表示されます。

## <a name="manage-access"></a>アクセスを管理する 

1. Customer または MSSP myaccess のアクセス要求を確認および承認します。

    アクセス要求は、MSSP アナリスト承認者グループのメンバーによって、お客様のマイ アクセスで管理されます。

    これを行うには、次を使用して顧客のマイアクセスにアクセスします  `https://myaccess.microsoft.com/@<Customer Domain >` 。 

    例:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. UI の [承認] セクションで要求 **を** 承認または拒否します。

     この時点で、アナリストのアクセスがプロビジョニングされ、各アナリストは顧客の Microsoft 365 セキュリティ センターにアクセスできる必要があります。 

    `https://security.microsoft.com/?tid=<CustomerTenantId>` 割り当てられたアクセス許可と役割を使用します。

> [!IMPORTANT]
> Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender への委任されたアクセスでは、現在、ブラウザーウィンドウごとに 1 つのテナントにアクセスできます。 