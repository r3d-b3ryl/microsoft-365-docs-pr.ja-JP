---
title: Microsoft 365 のデバイス管理ロードマップ
keywords: Microsoft 365、Microsoft 365、Microsoft 365、モバイル デバイス管理、Intune
author: kelleyvice-msft
ms.author: kvice
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: デバイス管理をセットアップするためのロードマップは、Microsoft 365。
ms.openlocfilehash: 2155d33aa57da5bb80dbc83623ac87a94a300f28
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59165414"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Microsoft 365 のデバイス管理ロードマップ

Microsoft 365には、組織内のデバイスとアプリの管理に役立つ機能が含まれています。 モバイル デバイスの管理は、組織のリソースをセキュリティで保護し、保護するのに役立ちます。

デバイス管理には、次の 2 つのオプションがあります。

- [Microsoft Intune](#microsoft-intune)
- [基本的なモビリティとセキュリティ](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

モバイル デバイス管理またはモバイル Microsoft Intune管理を使用して組織へのアクセスを管理するには、このツールを使用します。 モバイル デバイスの管理は、ユーザーが Intune でデバイスを "登録" する場合です。 デバイスが登録された後は、管理対象デバイスです。したがって、組織のポリシー、ルール、および設定を受け取る可能性があります。 たとえば、特定のアプリのインストール、パスワード ポリシーの作成、VPN 接続のインストールなどです。

自分の個人用デバイスを持つユーザーは、自分のデバイスを登録したり、Intune と組織のポリシーで管理したりしたくない場合があります。 ただし、組織のリソースとデータを保護する必要があります。 このシナリオでは、モバイル アプリケーション管理を使用してアプリを保護できます。 たとえば、モバイル アプリケーション管理ポリシーを使用すると、ユーザーがデバイス上のオンラインのアカウントにアクセスするときに PIN を入力SharePointを使用できます。

また、個人用デバイスと組織が所有するデバイスを管理する方法も決定します。 デバイスの使い方に応じて、デバイスの扱い方を変えてほしい場合があります。

## <a name="basic-mobility-and-security"></a>基本的なモビリティとセキュリティ

これは、Microsoft 365に組み込まれるので、ユーザーのモバイル デバイス (iPhone、iPad、Android、携帯電話など) のセキュリティ保護と管理Windows役立ちます。 デバイスのセキュリティ ポリシーを作成および管理したり、リモートでデバイスをワイプしたり、詳細なデバイス レポートを参照できます。

## <a name="choose-between-the-two-options"></a>2 つのオプションの中から選択する

最適なデバイス管理オプションをより適切に評価するには、「Basic Mobility Security と Intune の間で選択する」 [を参照してください](/office365/securitycompliance/choose-between-mdm-and-intune)。

評価に基づいて、次の方法でデバイスの管理を開始します。

- [Intune](/mem/intune/fundamentals/planning-guide)
- [基本的なモビリティとセキュリティ](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a>ID とデバイスのアクセスに関する推奨事項

Microsoft では、セキュアで生産性の高い労働力を確保するために [ID とデバイスのアクセス](../security/office-365-security/microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。 デバイス アクセスの場合は、次の記事の推奨事項と設定を使用します。

- [前提条件](../security/office-365-security/identity-access-prerequisites.md)
- [共通 ID とデバイスのアクセス ポリシー](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Contoso 社がデバイス管理を行ったMicrosoft 365

架空の代表的な多国籍企業が、Microsoft 365 クラウド サービスを使用してモバイル デバイス管理インフラストラクチャを展開した方法については、「Contoso のモバイル デバイス管理」を[参照してください](contoso-mdm.md)。