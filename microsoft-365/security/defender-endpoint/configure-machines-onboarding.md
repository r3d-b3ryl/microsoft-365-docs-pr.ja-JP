---
title: Microsoft Defender for Endpointにオンボードされたデバイスを取得する
description: Intuneマネージド デバイスのオンボードを追跡してMicrosoft Defender for Endpointし、オンボード率を向上させます。
keywords: オンボード, Intune管理, Microsoft Defender for Endpoint, Microsoft Defender, Windows Defender, 構成管理
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6caaddc208e6f73de0f49ff6d419c335848ae439
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64466325"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointにオンボードされたデバイスを取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

オンボードされた各デバイスでは、追加のエンドポイントでの検出と対応 (EDR) センサーが追加され、ネットワーク内の侵害アクティビティに対する可視性が向上します。 また、オンボードにより、デバイスで脆弱なコンポーネントとセキュリティ構成の問題を確認でき、攻撃中に重大な修復アクションを受け取る可能性もあります。

デバイスのオンボードを追跡および管理する前に、

- [デバイスをIntune管理に登録する](configure-machines.md#enroll-devices-to-intune-management)
- [必要なアクセス許可があることを確認する](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a>保護されていないデバイスを検出して追跡する

**オンボード** カードでは、Defender for Endpoint に実際にオンボードしたWindows デバイスの数と、Intuneで管理されているWindows デバイスの合計数を比較することで、オンボード率の概要を大まかに示します。

:::image type="content" source="images/secconmgmt_onboarding_card.png" alt-text="デバイス構成管理オンボード カード" lightbox="images/secconmgmt_onboarding_card.png":::

*オンボードされたデバイスの合計数とIntune管理されているWindowsデバイスの合計数を示すカード*

> [!NOTE]
> Configuration Manager、オンボード スクリプト、またはIntune プロファイルを使用しないその他のオンボード方法を使用した場合、データの不一致が発生する可能性があります。 これらの不一致を解決するには、Defender for Endpoint オンボードに対応するIntune構成プロファイルを作成し、そのプロファイルをデバイスに割り当てます。

## <a name="onboard-more-devices-with-intune-profiles"></a>Intune プロファイルを使用してより多くのデバイスをオンボードする

Defender for Endpoint には、[Windows デバイスをオンボードするための](onboard-configure.md)便利なオプションがいくつか用意されています。 ただし、Intuneマネージド デバイスの場合は、Intune プロファイルを利用して、Defender for Endpoint センサーを簡単に展開してデバイスを選択し、これらのデバイスをサービスに効果的にオンボードできます。

**[オンボード**] カードで、[**その他のデバイスのオンボード**] を選択して、Intuneにプロファイルを作成して割り当てます。 このリンクをクリックすると、Intuneのデバイス コンプライアンス ページに移動します。これにより、オンボード状態の同様の概要が表示されます。

:::image type="content" source="images/secconmgmt_onboarding_1deviceconfprofile.png" alt-text="Intuneデバイス管理のMicrosoft Defender for Endpointデバイス コンプライアンス ページ" lightbox="images/secconmgmt_onboarding_1deviceconfprofile.png":::

*Intuneデバイス管理のデバイス コンプライアンス ページをMicrosoft Defender for Endpointする*

> [!TIP]
> または、**すべてのサービス> Intune >デバイス コンプライアンス> Microsoft Defender ATP** から [、Microsoft Azure ポータル](https://portal.azure.com/)の Defender for Endpoint オンボード コンプライアンス ページに移動することもできます。

> [!NOTE]
> 最新のデバイス データを表示する場合は、[ **ATP センサーのないデバイスの一覧**] をクリックします。

デバイス コンプライアンス ページで、Defender for Endpoint センサーの展開専用の構成プロファイルを作成し、そのプロファイルをオンボードするデバイスに割り当てます。 これを行うには、次のいずれかを行います。

- 定義済みの **デバイス構成プロファイルから開始するように ATP センサーを構成するには** 、[デバイス構成プロファイルの作成] を選択します。
- デバイス構成プロファイルを最初から作成します。

詳細については、[Intuneデバイス構成プロファイルを使用してデバイスを Defender for Endpoint にオンボードする方法について説明します](/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)。

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>関連項目

- [デバイスが正しく構成されていることを確認する](configure-machines.md)
- [Defender for Endpoint セキュリティ ベースラインへのコンプライアンスを強化する](configure-machines-security-baseline.md)
- [ASR ルールの展開と検出を最適化する](configure-machines-asr.md)
