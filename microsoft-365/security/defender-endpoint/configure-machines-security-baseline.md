---
title: Microsoft Defender for Endpointセキュリティ ベースラインへのコンプライアンスを強化する
description: Microsoft Defender for Endpointセキュリティ ベースラインは、最適な保護を提供するためにセキュリティ制御を設定します。
keywords: Intune管理、Microsoft Defender for Endpoint、Microsoft Defender、Microsoft Defender for Endpoint ASR、セキュリティ ベースライン
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
ms.openlocfilehash: 1980567c93364f35923a9a7f2433733e05878e61
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64467975"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a>Microsoft Defender for Endpointセキュリティ ベースラインへのコンプライアンスを強化する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

セキュリティ ベースラインにより、セキュリティの専門家と専門家Windowsシステム管理者のガイダンスに従ってセキュリティ機能が確実に構成されます。 デプロイされると、Defender for Endpoint セキュリティ ベースラインによって Defender for Endpoint セキュリティ制御が設定され、最適な保護が提供されます。

セキュリティ ベースラインと、構成プロファイルを使用してIntuneに割り当てられる方法については、[こちらの FAQ を参照してください](/intune/security-baselines#q--a)。

セキュリティ ベースラインへのコンプライアンスをデプロイして追跡する前に、次の手順を実行します。

- [デバイスをIntune管理に登録する](configure-machines.md#enroll-devices-to-intune-management)
- [必要なアクセス許可があることを確認する](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a>Microsoft Defender for EndpointとWindows Intuneセキュリティ ベースラインを比較する

Windows Intuneセキュリティ ベースラインには、ブラウザーの設定、PowerShell 設定、Microsoft Defender ウイルス対策などの一部のセキュリティ機能の設定など、Windowsを実行しているデバイスを安全に構成するために必要な包括的な推奨設定セットが用意されています。 これに対し、Defender for Endpoint ベースラインには、エンドポイントでの検出と対応 (EDR) の設定や、Windows Intuneセキュリティ ベースラインに含まれる設定など、Defender for Endpoint スタック内のすべてのセキュリティ制御を最適化する設定が用意されています。 各ベースラインの詳細については、次を参照してください。

- [Intuneのセキュリティ ベースライン設定をWindowsする](/intune/security-baseline-settings-windows)
- [Intuneのベースライン設定をMicrosoft Defender for Endpointする](/intune/security-baseline-settings-defender-atp)

理想的には、Defender for Endpoint にオンボーディングされたデバイスは、両方のベースラインで展開されます。最初に Windows を保護するための Windows Intune セキュリティ ベースラインと、次に Defender for Endpoint セキュリティ コントロールを最適に構成するために上に階層化された Defender for Endpoint セキュリティベースラインです。 リスクと脅威に関する最新のデータを活用し、ベースラインの進化に伴う競合を最小限に抑えるために、ベースラインの最新バージョンは、リリースされたらすぐにすべての製品に適用してください。

> [!NOTE]
> Defender for Endpoint セキュリティ ベースラインは物理デバイス用に最適化されており、現在、仮想マシン (VM) または VDI エンドポイントでの使用はお勧めしません。 特定のベースライン設定が、仮想化された環境でのリモート対話型セッションに影響を与える可能性があります。

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a>Defender for Endpoint セキュリティ ベースラインへのコンプライアンスを監視する

[デバイス構成管理](configure-machines.md)の **セキュリティ ベースライン** カードには、Defender for Endpoint セキュリティ ベースラインが割り当てられているWindows 10デバイスとWindows 11 デバイス全体のコンプライアンスの概要が表示されます。

:::image type="content" source="images/secconmgmt_baseline_card.png" alt-text="セキュリティ ベースライン カード" lightbox="images/secconmgmt_baseline_card.png":::

*Defender for Endpoint セキュリティ ベースラインへの準拠を示すカード*

各デバイスには、次のいずれかの状態の種類が与えられます。

- **ベースラインに一致** する: デバイス設定は、ベースライン内のすべての設定と一致します。
- **ベースラインと一致しない**: 少なくとも 1 つのデバイス設定がベースラインと一致しません。
- **正しく構成されていない**: 少なくとも 1 つのベースライン設定がデバイスで正しく構成されておらず、競合、エラー、または保留中の状態です。
- **該当なし**: デバイスでは、少なくとも 1 つのベースライン設定は適用されません。

特定のデバイスを確認するには、カードで **[セキュリティ ベースラインの構成** ] を選択します。 これにより、デバイス管理のIntuneが行われます。 そこから、デバイスの名前と状態に [ **デバイス** の状態] を選択します。

> [!NOTE]
> デバイス構成管理ページに表示される集計データと、Intuneの概要画面に表示される集計データに不一致が発生する場合があります。

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a>Microsoft Defender for Endpointセキュリティ ベースラインを確認して割り当てる

デバイス構成管理では、Microsoft Defender for Endpointセキュリティ ベースラインが特に割り当てられているWindows 10デバイスとWindows 11 デバイスのベースライン コンプライアンスのみが監視されます。 ベースラインを簡単に確認し、Intuneデバイス管理上のデバイスに割り当てることができます。

1. [**セキュリティ ベースライン**] カードの [**セキュリティ ベースライン** の構成] を選択して、Intuneデバイス管理に移動します。 ベースライン コンプライアンスの同様の概要が表示されます。

   > [!TIP]
   > または、Microsoft Azure ポータルの Defender for Endpoint セキュリティ ベースラインに移動して、**Microsoft Defender ATP ベースライン> Intune >デバイス セキュリティ>セキュリティ ベースライン>** します。

2. 新しいプロファイルを作成します。

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile1.png" alt-text="IntuneのMicrosoft Defender for Endpointセキュリティ ベースラインの概要の [プロファイルの作成] タブ" lightbox="images/secconmgmt_baseline_intuneprofile1.png":::<br>
   *IntuneのMicrosoft Defender for Endpointセキュリティ ベースラインの概要*

3. プロファイルの作成中に、ベースラインの特定の設定を確認して調整できます。

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile2.png" alt-text="Intuneでのプロファイル作成時のセキュリティ ベースライン オプション" lightbox="images/secconmgmt_baseline_intuneprofile2.png":::<br>
   *Intuneでのプロファイルの作成中のセキュリティ ベースライン オプション*

4. プロファイルを適切なデバイス グループに割り当てます。

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile3.png" alt-text="Intuneのセキュリティ ベースライン プロファイル" lightbox="images/secconmgmt_baseline_intuneprofile3.png":::<br>
   *Intuneでのセキュリティ ベースライン プロファイルの割り当て*

5. プロファイルを作成して保存し、割り当てられたデバイス グループに展開します。

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile4.png" alt-text="Intuneにセキュリティ ベースラインを割り当てる" lightbox="images/secconmgmt_baseline_intuneprofile4.png":::<br>
   *Intuneでのセキュリティ ベースライン プロファイルの作成*

> [!TIP]
> Intuneのセキュリティ ベースラインは、デバイスを包括的にセキュリティで保護し、保護するための便利な方法を提供します。 [Intuneのセキュリティ ベースラインの詳細について説明します](/intune/security-baselines)。

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>関連項目

- [デバイスが正しく構成されていることを確認する](configure-machines.md)
- [Microsoft Defender for Endpointにオンボードされたデバイスを取得する](configure-machines-onboarding.md)
- [ASR ルールの展開と検出を最適化する](configure-machines-asr.md)
