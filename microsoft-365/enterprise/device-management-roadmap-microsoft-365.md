---
title: Microsoft 365 のデバイス管理ロードマップ
keywords: Microsoft 365、エンタープライズ向けのMicrosoft 365、Microsoft 365ドキュメント、モバイル デバイス管理、Intune
author: kelleyvice-msft
ms.author: kvice
manager: scotv
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
description: Microsoft 365のデバイス管理を設定するためのロードマップ。
ms.openlocfilehash: eeed1a69fc1724f3feb75f4bc096cad3a3c25cf0
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095314"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Microsoft 365 のデバイス管理ロードマップ

企業向けのMicrosoft 365には、組織内のデバイスとそのアプリを管理するのに役立つ機能が含まれています。 モバイル デバイスの管理は、組織のリソースをセキュリティで保護するのに役立ちます。

デバイス管理には、次の 2 つのオプションがあります。

- [Microsoft Intune](#microsoft-intune)
- [基本的なモビリティとセキュリティ](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intuneを使用して、モバイル デバイス管理またはモバイル アプリケーション管理を使用して組織へのアクセスを管理できます。 モバイル デバイス管理は、ユーザーがデバイスをIntuneに "登録" するときです。 デバイスが登録されると、管理対象デバイスになります。そのため、組織のポリシー、ルール、および設定を受け取ることができます。 たとえば、特定のアプリのインストール、パスワード ポリシーの作成、VPN 接続のインストールなどを行うことができます。

自分の個人用デバイスを持つユーザーは、デバイスを登録したり、Intuneや組織のポリシーで管理したりしたくない場合があります。 ただし、組織のリソースとデータを保護する必要があります。 このシナリオでは、モバイル アプリケーション管理を使用してアプリを保護できます。 たとえば、モバイル アプリケーション管理ポリシーを使用すると、デバイス上の SharePoint Online にアクセスするときにユーザーが PIN を入力する必要があります。

また、個人用デバイスと組織所有のデバイスを管理する方法も決定します。 デバイスの用途に応じて、デバイスの扱い方が異なる場合があります。

## <a name="basic-mobility-and-security"></a>基本的なモビリティとセキュリティ

これはMicrosoft 365に組み込まれており、iPhone、iPad、Android、Windowsスマートフォンなどのユーザーのモバイル デバイスをセキュリティで保護して管理するのに役立ちます。 デバイスのセキュリティ ポリシーを作成および管理したり、リモートでデバイスをワイプしたり、詳細なデバイス レポートを参照できます。

## <a name="choose-between-the-two-options"></a>2 つのオプションから選択する

最適なデバイス管理オプションを適切に評価するには、「[基本的なモビリティ セキュリティとIntuneの選択](/office365/securitycompliance/choose-between-mdm-and-intune)」を参照してください。

評価に基づいて、次の方法でデバイスの管理を開始します。

- [Intune](/microsoft-365/solutions/manage-devices-with-intune-overview)
- [基本的なモビリティとセキュリティ](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a>ID とデバイスのアクセスに関する推奨事項

Microsoft では、セキュアで生産性の高い労働力を確保するために [ID とデバイスのアクセス](../security/office-365-security/microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。 デバイスへのアクセスには、次の記事の推奨事項と設定を使用します。

- [前提条件](../security/office-365-security/identity-access-prerequisites.md)
- [共通 ID とデバイスのアクセス ポリシー](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Contoso がMicrosoft 365のデバイス管理を行った方法

架空の代表的な多国籍企業が、Microsoft 365 クラウド サービスを使用してモバイル デバイス管理インフラストラクチャを展開した方法については、「[Contoso のモバイル デバイス管理](contoso-mdm.md)」を参照してください。