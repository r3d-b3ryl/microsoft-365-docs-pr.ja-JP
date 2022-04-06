---
title: Microsoft Defender for Endpoint セキュリティ ベースラインへのコンプライアンスを強化する
description: Microsoft Defender for Endpoint セキュリティ ベースラインは、最適な保護を提供するためにセキュリティ制御を設定します。
keywords: Intune 管理、Microsoft Defender for Endpoint、Microsoft Defender、Microsoft Defender for Endpoint ASR、セキュリティ ベースライン
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
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a>Microsoft Defender for Endpoint セキュリティ ベースラインへのコンプライアンスを強化する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

セキュリティベースラインは、セキュリティ専門家と専門家およびシステム管理者の両方からのガイダンスに従ってセキュリティ機能Windows確認します。 展開すると、Defender for Endpoint セキュリティ ベースラインは、最適な保護を提供するために Defender for Endpoint セキュリティ コントロールを設定します。

構成プロファイルを使用してセキュリティ基準と Intune に割り当てられる方法を理解するには、この [FAQ を参照してください](/intune/security-baselines#q--a)。

セキュリティ 基準へのコンプライアンスを展開して追跡する前に、次の方法を実行します。

- [Intune 管理にデバイスを登録する](configure-machines.md#enroll-devices-to-intune-management)
- [必要なアクセス許可を持っている必要があります。](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a>Microsoft Defender for Endpoint と Intune のセキュリティ ベースラインWindows比較する

Windows Intune のセキュリティ ベースラインには、ブラウザー設定、PowerShell 設定、Microsoft Defender ウイルス対策 などの一部のセキュリティ機能の設定など、Windows を実行しているデバイスを安全に構成するために必要な、一連の推奨設定が提供されています。 これに対し、Defender for Endpoint ベースラインには、エンドポイント検出と応答 (EDR) の設定や、Windows Intune のセキュリティ ベースラインにある設定など、Defender for Endpoint スタック内のすべてのセキュリティ コントロールを最適化する設定が用意されています。 各ベースラインの詳細については、以下を参照してください。

- [Windows Intune のセキュリティ 基準の設定](/intune/security-baseline-settings-windows)
- [Intune のエンドポイント基準設定用 Microsoft Defender](/intune/security-baseline-settings-defender-atp)

理想的には、Defender for Endpoint にオンボーディングされたデバイスは、両方のベースラインで展開されます。最初に Windows を保護するための Windows Intune セキュリティ ベースラインと、次に Defender for Endpoint セキュリティ コントロールを最適に構成するために上に階層化された Defender for Endpoint セキュリティベースラインです。 リスクと脅威に関する最新のデータを活用し、ベースラインの進化に伴う競合を最小限に抑えるために、ベースラインの最新バージョンは、リリースされたらすぐにすべての製品に適用してください。

> [!NOTE]
> Defender for Endpoint セキュリティ ベースラインは物理デバイス用に最適化されています。現在、仮想マシン (VM) または VDI エンドポイントでの使用は推奨されていません。 特定のベースライン設定が、仮想化された環境でのリモート対話型セッションに影響を与える可能性があります。

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a>Defender for Endpoint セキュリティ ベースラインへのコンプライアンスを監視する

デバイス **構成管理の** セキュリティ [](configure-machines.md) 基準カードは、Defender for Endpoint セキュリティ ベースラインが割り当てられている Windows 10 デバイスと Windows デバイス全体のコンプライアンスの概要を示します。

:::image type="content" source="images/secconmgmt_baseline_card.png" alt-text="セキュリティ ベースライン カード" lightbox="images/secconmgmt_baseline_card.png":::

*Defender for Endpoint セキュリティ ベースラインへの準拠を示すカード*

各デバイスには、次のいずれかの状態の種類が与えられます。

- **基準と一致**: デバイスの設定は、基準計画のすべての設定と一致します。
- **ベースラインと一致しない**: 少なくとも 1 つのデバイス設定がベースラインと一致しません。
- **構成ミス**: 少なくとも 1 つの基準設定がデバイスで適切に構成されていないので、競合、エラー、または保留中の状態です。
- **該当なし**: 少なくとも 1 つの基準計画設定がデバイスに適用できません。

特定のデバイスを確認するには、カード **の [セキュリティ 基準計画の構成** ] を選択します。 これにより、Intune デバイス管理にアクセスできます。 そこから、[デバイスの **状態]** を選択して、デバイスの名前と状態を指定します。

> [!NOTE]
> デバイス構成管理ページに表示される集計データと、Intune の概要画面に表示されるデータに不一致が発生する可能性があります。

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a>Microsoft Defender for Endpoint セキュリティ ベースラインの確認と割り当て

デバイス構成管理は、Microsoft Defender for Endpoint セキュリティ ベースラインWindows 10割りWindows 11 台のデバイスの基準準拠のみを監視します。 ベースラインを簡単に確認し、Intune デバイス管理のデバイスに割り当てできます。

1. [ **セキュリティ ベースライン カードのセキュリティ** 基準を構成 **する] を選択** して、Intune デバイス管理に移動します。 ベースラインコンプライアンスの同様の概要が表示されます。

   > [!TIP]
   > または、Microsoft Defender ATP ベースラインのすべてのサービス **> Intune** > デバイス セキュリティ > セキュリティ ベースライン>から、Microsoft Azure ポータルの Defender for Endpoint セキュリティ ベースラインに移動できます。

2. 新しいプロファイルを作成します。

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile1.png" alt-text="Intune の Microsoft Defender for Endpoint セキュリティ ベースラインの概要にある [プロファイルの作成] タブ" lightbox="images/secconmgmt_baseline_intuneprofile1.png":::<br>
   *Intune の Microsoft Defender for Endpoint セキュリティ ベースラインの概要*

3. プロファイルの作成中に、基準計画の特定の設定を確認および調整できます。

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile2.png" alt-text="Intune でのプロファイル作成時のセキュリティ基準オプション" lightbox="images/secconmgmt_baseline_intuneprofile2.png":::<br>
   *Intune でのプロファイル作成時のセキュリティ基準オプション*

4. プロファイルを適切なデバイス グループに割り当てる。

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile3.png" alt-text="Intune のセキュリティ ベースライン プロファイル" lightbox="images/secconmgmt_baseline_intuneprofile3.png":::<br>
   *Intune でのセキュリティ 基準プロファイルの割り当て*

5. プロファイルを作成して保存し、割り当てられたデバイス グループに展開します。

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile4.png" alt-text="Intune でのセキュリティ 基準の割り当て" lightbox="images/secconmgmt_baseline_intuneprofile4.png":::<br>
   *Intune でのセキュリティ ベースライン プロファイルの作成*

> [!TIP]
> Intune のセキュリティ ベースラインは、デバイスを包括的に保護して保護するための便利な方法を提供します。 [Intune のセキュリティ基準について詳しくは、をご覧ください](/intune/security-baselines)。

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>関連項目

- [デバイスが正しく構成されていることを確認する](configure-machines.md)
- [Microsoft Defender for Endpoint にオンボードされているデバイスを取得する](configure-machines-onboarding.md)
- [ASR ルールの展開と検出を最適化する](configure-machines-asr.md)
