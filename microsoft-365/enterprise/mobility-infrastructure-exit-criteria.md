---
title: モバイルデバイス管理インフラストラクチャの終了条件
description: microsoft 365 Enterprise には、microsoft Intune を使用したモバイルデバイス管理が含まれます。 要件と前提条件を確認し、Azure Active Directory リソースを使用して Intune を設定し、iOS、macOS、Android、および Windows デバイスを登録し、アプリを展開し、構成プロファイルを作成し、コンプライアンスポリシーを使用して、モバイルの条件付きアクセスを有効にします。Microsoft 365 Enterprise を使用したデバイス管理。
keywords: microsoft 365、microsoft 365 Enterprise、microsoft 365 ドキュメント、モバイルデバイス管理、Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 14f216fe352d9108fe69028731f4c94dfb9d19f7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291234"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>モバイルデバイス管理インフラストラクチャの終了条件

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*これは、Microsoft 365 Enterprise の E3 および E5 バージョンに適用されます。*

構成が、モバイルデバイス管理インフラストラクチャの次の要件を満たしていることを確認します。

- デバイス向けの組織のルールを適用するために、Azure AD ユーザーとグループの作成を含めて Intune が設定されます。
- 作成したポリシーをデバイスが受信できるように、Intune にデバイスを登録しました。
- アプリはデバイスに追加されるので、ユーザーは Exchange Online や SharePoint Online など、組織の Microsoft 365 のクラウド サービスにアクセスできます。
- 機能と設定は、作成した Azure AD ユーザーとグループを使用してデバイスに構成および適用されます。これにはウイルス対策の有効化や特定アプリの制限が含まれます。
- デバイスでファイアウォールやパスワードの長さを要求するようにコンプライアンス ポリシーが設定されています。準拠していないデバイスの場合、条件付きアクセスによって組織のデータへのアクセスをブロックします。



## <a name="results-and-next-steps"></a>結果と次の手順

デバイスは Intune に登録され、適切なポリシーで構成されます。

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| Microsoft 365 Enterprise のエンドツーエンドの展開のフェーズに従っている場合、次のフェーズは[情報保護](infoprotect-infrastructure.md)です。 |
