---
title: Exchange Online がメールの機密情報をセキュリティで保護する方法
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Microsoft 365 Office 365 のセキュリティ、プライバシー、コンプライアンス情報を提供する Office 365 セキュリティ センターに加えて、Microsoft がデータセンターに保存するシークレットを保護する方法を知りたい場合があります。 分散キー マネージャー (DKM) というテクノロジを使用します。
ms.openlocfilehash: 01c254da55e4e9c27b2a4d8423a8f3d4dce3812c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194431"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Exchange Online がメールの機密情報をセキュリティで保護する方法

この記事では、Microsoft がデータセンターで電子メール シークレットをセキュリティで保護する方法について説明します。
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>お客様が提供する秘密情報をセキュリティで保護する方法

Office 365 のセキュリティ、プライバシー、コンプライアンス情報を提供する[Office 365](./get-started-with-service-trust-portal.md)セキュリティ センターに加えて、Microsoft がデータセンターで提供するシークレットを保護する方法を知りたい場合があります。 分散キー マネージャー (DKM) というテクノロジを使用します。
  
[分散キー マネージャー](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) は、一連のシークレット キーを使用して情報を暗号化および復号化するクライアント側の機能です。 DKM で暗号化されたデータを復号化するには、Active Directory ドメイン サービスの特定のセキュリティ グループのメンバーだけがこれらのキーにアクセスできます。 Exchange Online では Exchange プロセスの実行に使用する特定のサービス アカウントだけが、そのセキュリティ グループに属します。 データセンター内の標準運用手順の一環として、このセキュリティ グループに属する資格情報は人間には付与されないため、人間はだれもこれらの機密情報を解読できるキーにアクセスできません。
  
デバッグ、トラブルシューティング、または監査の目的で、データセンター管理者は、セキュリティ グループの一部である一時的な資格情報を取得するために、管理者特権でのアクセスを要求する必要があります。 このプロセスでは、複数のレベルの法的承認が必要です。 アクセスが許可されている場合、すべてのアクティビティがログに記録され、監査されます。 さらに、アクセスは、自動的に期限切れになる一定の間隔でのみ付与されます。
  
特別な保護のために、DKM テクノロジには自動キー ロールオーバーとアーカイブが含まれています。 これにより、同じキーに無期限に依存することなく、古いコンテンツに引き続きアクセスできます。
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>DKM をExchange Onlineする場所

Microsoft では、[分散キー マネージャーを](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)使用して、データ センター内のExchange Online暗号化します。 次に例を示します。
  
- 接続されたアカウントの電子メール アカウント資格情報。 接続されたアカウントは、アプリ、Gmail、Yahoo などのHotmailサード パーティのアカウントです。 メール アカウント。

- 顧客キー。 顧客キーで [サービス暗号化を使用している場合](customer-key-overview.md)は [、Azure Key Vault](/azure/key-vault/key-vault-whatis) を使用してシークレットを保護します。

## <a name="related-topics"></a>関連トピック

[Office 365 での暗号化](encryption.md)
  
[暗号化についてのテクニカル リファレンスの詳細](technical-reference-details-about-encryption.md)
  
[セキュリティ コンプライアンス センター &amp; のサービス アシュアランス](./service-assurance.md)
