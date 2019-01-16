---
title: モバイル デバイス管理インフラストラクチャの終了条件
description: Microsoft 365 エンタープライズには、Microsoft Intune を使用してモバイル デバイスの管理が含まれています。要件と前提条件を確認、Intune は、Azure Active Directory リソースを使用して設定、macOS、iOS、Android、および Windows の登録、デバイス、アプリケーションを展開、構成プロファイルを作成、コンプライアンス ・ ポリシーを使用および携帯用の条件付きのアクセスを有効にします。Microsoft 365 エンタープライズ ・ デバイスの管理です。
keywords: Microsoft 365、Microsoft 365 エンタープライズでは、Microsoft 365 マニュアル、モバイル デバイスの管理、Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/10/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: b511052698f42a07df5fc25aeaad7fc7f00c2a6e
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869170"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>モバイル デバイス管理インフラストラクチャの終了条件

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*Microsoft 365 エンタープライズの E3、E5 のバージョンに適用されます。*

展開プロセスの次の段階移動する前に、構成がモバイル デバイス管理のインフラストラクチャについて次の要件を満たしているを確認します。

- デバイス向けの組織のルールを適用するために、Azure AD ユーザーとグループの作成を含めて Intune が設定されます。
- 作成したポリシーをデバイスが受信できるように、Intune にデバイスを登録しました。
- アプリはデバイスに追加されるので、ユーザーは Exchange Online や SharePoint Online など、組織の Microsoft 365 のクラウド サービスにアクセスできます。
- 機能と設定は、作成した Azure AD ユーザーとグループを使用してデバイスに構成および適用されます。これにはウイルス対策の有効化や特定アプリの制限が含まれます。
- デバイスでファイアウォールやパスワードの長さを要求するようにコンプライアンス ポリシーが設定されています。準拠していないデバイスの場合、条件付きアクセスによって組織のデータへのアクセスをブロックします。

## <a name="next-phase"></a>次のフェーズ

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| Microsoft 365 エンタープライズのエンド ・ ツー ・ エンドの展開のプロセスで、次の段階は、[情報の保護](infoprotect-infrastructure.md)です。 |
