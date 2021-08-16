---
title: Microsoft Defender for Identity の評価環境を有効にする
description: Microsoft Defender for Identity を Microsoft 365 Defender試用版ラボまたはパイロット環境でセットアップするには、&センサーをインストールし、他のコンピューターにローカル管理者を検出します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 93c3b15dc9ee47c076d4f17a60530d6660dea112
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58247183"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a>Microsoft Defender for Identity の評価環境を有効にする

**適用対象:**
- Microsoft 365 Defender

この記事は、Microsoft Defender for Identity の評価環境をセットアップする手順 [2/2](eval-defender-identity-overview.md) です。 このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-identity-overview.md)。

次の手順を使用して、Microsoft Defender for Identity 環境をセットアップします。 

![Microsoft Defender 評価環境で Microsoft Defender for Identity を有効にする手順](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [手順 1.Id インスタンスの Defender をセットアップする](#step-1-set-up-the-defender-for-identity-instance)
- [手順 2.センサーのインストールと構成](#step-2-install-and-configure-the-sensor)
- [手順 3.センサーを使用してコンピューターのイベント ログとプロキシ設定を構成する](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [手順 4.Defender for Identity で他のコンピューター上のローカル管理者を識別する許可](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a>手順 1。 Id インスタンスの Defender をセットアップする

Defender for Identity ポータルにサインインしてインスタンスを作成し、このインスタンスを Active Directory 環境に接続します。 

|  |手順     |詳細  |
|---------|---------|---------|
|1      | Defender for Identity インスタンスを作成する        | [クイック スタート: Microsoft Defender for Identity インスタンスを作成する](/defender-for-identity/install-step1)        |
|2      | Connect Defender for Identity インスタンスを Active Directory フォレストに移動する   | [クイック スタート: Connect Active Directory フォレストにアクセスする](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a>手順 2。 センサーのインストールと構成

次に、ドメイン コントローラーおよびオンプレミス環境の FS AD Defender for Identity センサーをダウンロード、インストール、および構成します。

|  |手順     |詳細  |
|---------|---------|---------|
|1      | 必要な Microsoft Defender for Identity センサーの数を決定します。        | [Microsoft Defender for Identity の容量を計画する](/defender-for-identity/capacity-planning)   |
|2      | センサー セットアップ パッケージをダウンロードする  |  [クイック スタート: Microsoft Defender for Identity センサーセットアップ パッケージをダウンロードする](/defender-for-identity/install-step3)   |
|3      | Defender for Identity センサーのインストール    |  [クイック スタート: Microsoft Defender for Identity センサーのインストール](/defender-for-identity/install-step4)       |
|4      | センサーを構成する       |  [Microsoft Defender for Identity センサーの設定を構成する ](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a>手順 3. センサーを使用してコンピューターのイベント ログとプロキシ設定を構成する

センサーをインストールしたコンピューターで、検出機能を有効Windows強化するために、イベント ログ コレクションとインターネット プロキシ設定を構成します。

|  |手順     |詳細  |
|---------|---------|---------|
|1      | イベント Windowsコレクションを構成する         | [イベント コレクションWindows構成する](/defender-for-identity/configure-windows-event-collection)        |
|2      | インターネット プロキシ設定の構成        | [Microsoft Defender for Identity Sensor のエンドポイント プロキシとインターネット接続の設定を構成する](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a>手順 4. Defender for Identity で他のコンピューター上のローカル管理者を識別する許可

Microsoft Defender for Identity 横移動パスの検出は、特定のコンピューター上のローカル管理者を識別するクエリに依存します。 これらのクエリは、Defender for Identity Service アカウントを使用して SAM-R プロトコルを使用して実行されます。 

Windows クライアントとサーバーで Defender for Identity アカウントが SAM-R を実行するようにするには、ネットワーク アクセス ポリシーに記載されている構成済みのアカウントに加えて、Defender for Identity サービス アカウントを追加するためにグループ ポリシーを変更する必要があります。 ドメイン コントローラーを除くすべてのコンピューターにグループ ポリシー **を適用してください**。

これを行う方法については [、「Configure Microsoft Defender for Identity to make remote calls to SAM](/defender-for-identity/install-step8-samr)」を参照してください。 

## <a name="next-steps"></a>次の手順

手順 3 / 3: [Id の Microsoft Defender のパイロット](eval-defender-identity-pilot.md)

Id の Microsoft Defender の [評価の概要に戻る](eval-defender-identity-overview.md)

[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)