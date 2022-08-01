---
title: Microsoft Defender for Endpointを使用して Microsoft Defender for IoT をオンボードする
description: Microsoft Defender for IoT にオンボードして、IoT デバイスに焦点を当てた可視性とセキュリティ評価を得ます。
keywords: siem コネクタ、siem、コネクタ、セキュリティ情報、イベントを有効にする
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 460988f063eb23c53ce76359da6ba7875ab3bc62
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67107131"
---
# <a name="onboard-with-microsoft-defender-for-iot"></a>Microsoft Defender for IoT でオンボードする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint P2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

Microsoft Defender for Endpointが Microsoft Defender for IoT とシームレスに統合されるようになりました。 この統合により、Defender for IoT によって提供されるエージェントレス監視機能を使用して、デバイス検出機能が拡張されます。 これにより、Voice over Internet Protocol (VoIP) デバイス、プリンター、カメラなど、IT ネットワークに接続されたエンタープライズ IoT デバイスのセキュリティ保護に役立ちます。 これにより、組織は、すべての IoT と運用テクノロジ (OT) インフラストラクチャをセキュリティで保護する 1 つの統合ソリューションを利用できます。 詳細については、「 [Enterprise IoT ネットワーク保護](/azure/defender-for-iot/organizations/overview-eiot)」を参照してください。

Defender for IoT プランを定義し、Enterprise IoT ネットワーク センサーを設定すると、デバイス データは Defender for Endpoint ポータルと Defender for IoT ポータルの両方へのストリーミングを自動的に開始します。 

Defender for IoT 統合により、可視性が向上し、ネットワーク内の IoT デバイスの特定、識別、セキュリティ保護に役立ちます。 これにより、IT デバイスの残りの部分 (ワークステーション、サーバー、モバイル) と共に、完全な OT/IoT インベントリの 1 つの統合ビューが提供されます。

Defender for IoT にオンボードしたお客様には、IoT デバイスの脆弱性評価と構成ミスに関するセキュリティに関する推奨事項もあります。

## <a name="prerequisites"></a>前提条件

Defender for Endpoint 統合の設定を変更するには、ユーザーに次のロールが必要です。

- Azure Active Directory のテナント グローバル管理者
- Microsoft Defender for IoT 統合に使用される Azure サブスクリプションのセキュリティ管理者

## <a name="onboard-a-defender-for-iot-plan"></a>Defender for IoT プランのオンボード

1. ポータルの [https://security.microsoft.com](https://security.microsoft.com/)ナビゲーション ウィンドウで、[**デバイス検出** \> **エンタープライズ IoT** の **設定]** \> を選択します。

1. プランに対して次のオプションを選択します。

   - プランを追加する Azure Active Directory テナントで使用可能なサブスクリプションの一覧から Azure サブスクリプションを選択します。

   - 料金プラン、月次または年間コミットメント、または試用版を選択します。 Microsoft Defender for IoT では、評価目的で最初の 1,000 台のコミット済みデバイスに対して 30 日間の無料試用版を提供しています。

      詳細については、 [Microsoft Defender for IoT の価格に関するページを](https://azure.microsoft.com/pricing/details/iot-defender/)参照してください。
   
   - 監視するコミット済みデバイスの数を選択します。 試用版を選択した場合、このセクションは既定で 1,000 台のデバイスを使用している場合は表示されません。

## <a name="set-up-a-network-sensor"></a>ネットワーク センサーを設定する

ネットワーク センサーを設定するには、 [前述](#onboard-a-defender-for-iot-plan)のように、Azure サブスクリプションに、Enterprise IoT デバイスが追加された Defender for IoT プランが必要です。

ネットワーク センサーを追加するには、[ **ネットワーク センサーのセットアップ** ] で **Microsoft Defender for IoT** リンクを選択します。 これにより、Azure portalのオンボード センサーのセットアップ プロセスが表示されます。 詳細については、「 [Enterprise IoT の概要](/azure/defender-for-iot/organizations/tutorial-getting-started-eiot-sensor)」を参照してください。

## <a name="managing-your-iot-devices"></a>IoT デバイスの管理

[Microsoft 365 Defender ポータル](https://security.microsoft.com/)で IoT デバイスを表示および管理するには、[**エンドポイント**] ナビゲーション メニューの **[デバイス インベントリ**] に移動し、[**IoT デバイス**] タブを選択します。

Defender for IoT でデバイスを表示する方法については、「組織のデバイス [インベントリを使用して IoT デバイスを管理する](/azure/defender-for-iot/organizations/how-to-manage-device-inventory-for-organizations)」を参照してください。


## <a name="view-devices-alerts-recommendations-and-vulnerabilities"></a>デバイス、アラート、推奨事項、および脆弱性を表示する

プランを定義し、ネットワーク センサーを設定した後、検出されたデータとセキュリティ評価を次の場所に表示します。

- Defender for Endpoint または Defender for IoT でデバイス データを表示する
- Defender for Endpoint のアラート、推奨事項、および脆弱性を表示する

詳細については、 [Defender for IoT の価格に関するページを](https://azure.microsoft.com/pricing/details/iot-defender/)参照してください。 

## <a name="cancel-your-defender-for-iot-plan"></a>Defender for IoT プランをキャンセルする

ポータルの Defender for Endpoint 設定ページから Defender for IoT プランを [https://security.microsoft.com](https://security.microsoft.com/) キャンセルします。 プランを取り消すと、統合が停止し、Defender for Endpoint でセキュリティ評価の値を取得したり、Defender for IoT で新しいデバイスを検出したりできなくなります。

## <a name="see-also"></a>関連項目

- [デバイス検出の概要](configure-device-discovery.md)
- [デバイス検出に関する FAQ](device-discovery-faq.md)
