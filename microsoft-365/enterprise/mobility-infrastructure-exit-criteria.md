---
title: モバイルデバイス管理インフラストラクチャの終了条件
description: Microsoft 365 Enterprise には、Microsoft Intune を使用したモバイルデバイス管理が含まれます。 要件と前提条件を確認し、Azure Active Directory リソースを使用して Intune を設定し、iOS、macOS、Android、および Windows デバイスを登録し、アプリを展開し、構成プロファイルを作成し、コンプライアンスポリシーを使用して、モバイルの条件付きアクセスを有効にします。Microsoft 365 Enterprise を使用したデバイス管理。
keywords: Microsoft 365、Microsoft 365 Enterprise、Microsoft 365 ドキュメント、モバイルデバイス管理、Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: e8f8f53224b334f92142e2c03ed05eaa9e38787a
ms.sourcegitcommit: d4aa94716b33e6c270ae7adfbdc4c19cf4a0087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "37385724"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>モバイルデバイス管理インフラストラクチャの終了条件

![フェーズ 5: モバイルデバイスの管理](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*これは、Microsoft 365 Enterprise の E3 および E5 バージョンに適用されます。*

構成が、モバイルデバイス管理インフラストラクチャの次の要件を満たしていることを確認します。

- Intune がセットアップされています。これにより、Azure Active Directory (Azure AD) ユーザーとグループを作成して、組織のデバイスに対するルールを適用します。
- 作成したポリシーをデバイスが受信できるように、Intune にデバイスを登録しました。
- アプリはデバイスに追加されるので、ユーザーは Exchange Online や SharePoint Online など、組織の Microsoft 365 のクラウド サービスにアクセスできます。
- 機能と設定は、作成した Azure AD ユーザーとグループを使用してデバイスに構成および適用されます。これにはウイルス対策の有効化や特定アプリの制限が含まれます。
- コンプライアンスポリシーは、デバイスでファイアウォールまたはパスワードの長さを要求するために配置されます。 デバイスが準拠していない場合、条件付きアクセスでは組織のデータへのアクセスがブロックされます。

## <a name="results-and-next-steps"></a>結果と次のステップ

デバイスは Intune に登録され、適切なポリシーで構成されます。

|||
|:-------|:-----|
|![フェーズ 6: 情報保護](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| Microsoft 365 Enterprise のエンドツーエンドの展開のフェーズに従っている場合、次のフェーズは[情報保護](infoprotect-infrastructure.md)です。 |
