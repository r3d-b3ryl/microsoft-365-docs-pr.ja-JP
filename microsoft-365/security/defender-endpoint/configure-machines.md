---
title: デバイスが正しく構成されていることを確認する
description: 脅威に対する全体的な回復性を高め、攻撃を検出して対応する機能を強化するようにデバイスを適切に構成します。
keywords: オンボード, Intune管理, Microsoft Defender for Endpoint, Microsoft Defender, Windows Defender, 攻撃面の削減, ASR, セキュリティ ベースライン
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
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 47c3cb5d680899a28e6467b24ef398a428851a07
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476161"
---
# <a name="ensure-your-devices-are-configured-properly"></a>デバイスが正しく構成されていることを確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

適切に構成されたデバイスを使用すると、脅威に対する全体的な回復性を高め、攻撃を検出して対応する機能を強化できます。 セキュリティ構成管理は、デバイスが次のことを確実に行うのに役立ちます。

- Microsoft Defender for Endpoint にオンボードする
- Defender for Endpoint セキュリティ ベースラインの構成を満たすか、またはそれを超える
- 戦略的な攻撃面の軽減策を実施する

ナビゲーション メニューの **[構成管理** ] をクリックして、[デバイス構成管理] ページを開きます。

:::image type="content" source="images/secconmgmt_main.png" alt-text="[セキュリティ構成管理] ページ" lightbox="images/secconmgmt_main.png":::

*デバイス構成管理ページ*

組織レベルで構成の状態を追跡し、Microsoft Intuneおよび<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>のデバイス管理ページへの直接の詳細なリンクを使用して、オンボードカバレッジの不十分さ、コンプライアンスの問題、不適切に最適化された攻撃面の軽減策に対応して迅速にアクションを実行できます。

そうすることで、次の利点があります。

- デバイス上のイベントの包括的な可視性
- 未加工のイベントを処理し、侵害アクティビティと脅威インジケーターを特定するための堅牢な脅威インテリジェンスと強力なデバイス ラーニング テクノロジ
- 悪意のある移植片のインストール、システム ファイルとプロセスのハイジャック、データ流出、その他の脅威アクティビティを効率的に停止するように構成されたセキュリティ機能の完全なスタック
- 攻撃面の軽減策を最適化し、脅威アクティビティに対する戦略的防御を最大化しながら、生産性への影響を最小限に抑える

## <a name="enroll-devices-to-intune-management"></a>Intune管理にデバイスを登録する

デバイス構成管理は、Intuneデバイス管理と密接に連携して、組織内のデバイスのインベントリとベースライン セキュリティ構成を確立します。 Intuneマネージド Windows デバイスの構成の問題を追跡および管理できます。

デバイスが正しく構成されていることを確認する前に、デバイスをIntune管理に登録します。 Intune登録は堅牢で、Windows デバイス用のいくつかの登録オプションがあります。 Intune登録オプションの詳細については、[Windows デバイスの登録の設定](/intune/windows-enroll)に関するページを参照してください。

> [!NOTE]
> WindowsデバイスをIntuneに登録するには、管理者に既にライセンスが割り当てられている必要があります。 [デバイスを登録するためのライセンス割り当て](/intune/licenses-assign)に関するページを参照してください。

> [!TIP]
> Intuneを使用してデバイス管理を最適化するには、[Intuneを Defender for Endpoint に接続します](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。

## <a name="obtain-required-permissions"></a>必要なアクセス許可を取得する

既定では、デバイスのオンボードとセキュリティ ベースラインの展開に必要なデバイス構成プロファイルを管理および割り当てることができるのは、Azure ADのグローバル管理者ロールまたは Intune サービス管理者ロールが割り当てられているユーザーだけです。

他のロールが割り当てられている場合は、必要なアクセス許可があることを確認します。

- デバイス構成に対する完全なアクセス許可
- セキュリティ ベースラインに対する完全なアクセス許可
- デバイス コンプライアンス ポリシーに対する読み取りアクセス許可
- 組織に対する読み取りアクセス許可

:::image type="content" source="images/secconmgmt_intune_permissions.png" alt-text="Intune に必要なアクセス許可" lightbox="images/secconmgmt_intune_permissions.png":::

*Intuneに対するデバイス構成のアクセス許可*

> [!TIP]
> Intuneに対するアクセス許可の割り当ての詳細については、[カスタム ロールの作成に関するページを参照](/intune/create-custom-role#to-create-a-custom-role)してください。

## <a name="in-this-section"></a>このセクションの内容

トピック|説明
:---|:---
[Defender for Endpoint にオンボードされたデバイスを取得する](configure-machines-onboarding.md)|Intuneマネージド デバイスのオンボード状態を追跡し、Intuneを介してより多くのデバイスをオンボードします。 
[Defender for Endpoint セキュリティ ベースラインへのコンプライアンスを強化する](configure-machines-security-baseline.md)|ベースラインコンプライアンスと非準拠を追跡します。 セキュリティ ベースラインを、より多くのIntuneマネージド デバイスにデプロイします。
[ASR ルールの展開と検出を最適化する](configure-machines-asr.md)|<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>の影響分析ツールを使用して、ルールのデプロイを確認し、検出を調整します。

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
