---
title: Defender for Endpoint onboarding Windows Server
description: Windows Server をMicrosoft Defender for Endpointにオンボードします。
keywords: オンボード, Microsoft Defender for Endpointオンボード, sccm, グループ ポリシー, mdm, ローカル スクリプト, 検出テスト
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b25d60be243dd5d375fb6ed0f795e4a901a504b2
ms.sourcegitcommit: c6f1486617b39565bfd8f662ee6ad65a9cefd3e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66532773"
---
# <a name="defender-for-endpoint-onboarding-windows-server"></a>Defender for Endpoint onboarding Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- Windows Server 2012 R2
- Windows Server 2016
- Windows サーバー半期エンタープライズ チャネル
- Windows Server 2019 以降
- Windows Server 2019 Core Edition
- Windows Server 2022
- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https:%2F%2Faka.ms%2FMDEp2OpenTrial)

サポートされているデバイスのいずれかをオンボードするには、Defender for Endpoint ポータルのオンボード セクションを確認する必要があります。 デバイスに応じて、適切な手順と、デバイスに適した管理および展開ツールのオプションが提供されます。

Defender for Endpoint では、サポートが拡張され、Windows サーバー オペレーティング システムも含まれます。 このサポートにより、Microsoft 365 Defender コンソールを介して高度な攻撃の検出と調査の機能がシームレスに提供されます。 Windows Server のサポートにより、サーバーアクティビティに関するより深い分析情報、カーネルとメモリの攻撃検出の対象範囲が提供され、対応アクションが可能になります。

このトピックでは、特定の Windows サーバーを Microsoft Defender for Endpoint にオンボードする方法について説明します。

Windows サーバーのWindows セキュリティベースラインをダウンロードして使用する方法のガイダンスについては、「[Windows セキュリティ 基準計画](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-baselines)」を参照してください。

## <a name="windows-server-onboarding-overview"></a>Windows サーバーのオンボードの概要

サーバー 2008 R2、2012 R2、2016、2019、2022 を正常にオンボードするには、次の一般的な手順を完了する必要があります。

:::image type="content" source="images/server-onboarding.png" alt-text="サーバーオンボーディング" lightbox="images/server-onboarding.png":::

> [!NOTE]
> サーバーは、GP のみを使用してオンボードされます。

### <a name="windows-server-2012-r2-and-windows-server-2016"></a>Windows Server 2012 R2 および Windows Server 2016
- インストール パッケージとオンボード パッケージをダウンロードします。
- インストール パッケージを適用します。
- 対応するツールのオンボード手順に従います。

### <a name="windows-server-semi-annual-enterprise-channel-and-windows-server-2019"></a>Windows サーバー半期エンタープライズ チャネルと Windows サーバー 2019
- オンボード パッケージをダウンロードします。
- 対応するツールのオンボード手順に従います。

> [!IMPORTANT]
> Microsoft Defender for Endpoint Server SKU を購入するためには、以下のいずれか、Windows E5/A5、Microsoft 365 E5/A5、Microsoft 365 E5 Security のサブスクリプションライセンスを組み合わせて購入しておくことが必要です。 ライセンスの詳細については、「[製品使用条件](https://www.microsoft.com/licensing/terms/productoffering/MicrosoftDefenderforEndpointServer/all)」 を参照してください。

## <a name="offboard-windows-servers"></a>Windows サーバーのオフボード

R2、Windows Server 2016、Windows Server (SAC)、Windows Server 2019、および Windows Server 2019 Core エディションWindows Server 2012、Windows 10 クライアント デバイスで使用できるのと同じ方法でオフボードできます。

- [構成マネージャーを使用してデバイスをオフボードする](/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#offboard-devices-using-configuration-manager)
- [モバイル デバイス管理 ツールを使用してデバイスをオフボードおよび監視する](/microsoft-365/security/defender-endpoint/configure-endpoints-mdm#offboard-and-monitor-devices-using-mobile-device-management-tools)
- [グループ ポリシーを使用してデバイスをオフボードする](/microsoft-365/security/defender-endpoint/configure-endpoints-gp#offboard-devices-using-group-policy)
- [ローカル スクリプトを使用してデバイスをオフボードする](/microsoft-365/security/defender-endpoint/configure-endpoints-script#offboard-devices-using-a-local-script)

オフボーディング後は、Windows Server 2012 R2 とWindows Server 2016で統合ソリューション パッケージをアンインストールできます。

他の Windows サーバー バージョンの場合、サービスから Windows サーバーをオフボードするには、次の 2 つのオプションがあります。
- MMA エージェントをアンインストールする
- Defender for Endpoint ワークスペースの構成を削除する

> [!NOTE]
> MMA を必要とする Windows Server 2016 および Windows Server 2012 R2 用の以前の Microsoft Defender for Endpoint を実行している場合は、他の Windows サーバー バージョンのこれらのオフボード手順も適用されます。 新しい統合ソリューションに移行する手順は、「[Microsoft Defender for Endpoint のサーバー移行シナリオ](/microsoft-365/security/defender-endpoint/server-migration)」 にあります。

## <a name="related-topics"></a>関連項目

- [Microsoft Endpoint Configuration Manager を使用した Windows デバイスのオンボード](configure-endpoints-sccm.md)
- [グループ ポリシーを使用してデバイスをオンボードする](configure-endpoints-gp.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](configure-endpoints-vdi.md)
