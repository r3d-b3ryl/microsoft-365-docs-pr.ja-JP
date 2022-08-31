---
title: Microsoft Defender for Identityの評価環境を有効にする
description: Microsoft 365 Defender試用版ラボまたはパイロット環境でMicrosoft Defender for Identityを設定するには、センサーの構成&インストールし、他のコンピューターでローカル管理者を検出します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: conceptual
ms.openlocfilehash: 800410fe4faecde9a104242d5d4a1821ad8de86a
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482254"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a>Microsoft Defender for Identityの評価環境を有効にする

**適用対象:**
- Microsoft 365 Defender

この記事は、Microsoft Defender for Identityの評価環境を設定する手順 [2/2](eval-defender-identity-overview.md) です。 このプロセスの詳細については、 [概要に](eval-defender-identity-overview.md)関する記事を参照してください。

Microsoft Defender for Identity環境を設定するには、次の手順に従います。 

:::image type="content" source="../../media/defender/m365-defender-identity-eval-enable-steps.png" alt-text="Microsoft Defender 評価環境でMicrosoft Defender for Identityを有効にする手順" lightbox="../../media/defender/m365-defender-identity-eval-enable-steps.png":::

- [手順 1.Defender for Identity Instance を設定する](#step-1-set-up-the-defender-for-identity-instance)
- [手順 2.センサーをインストールして構成する](#step-2-install-and-configure-the-sensor)
- [手順 3.センサーを使用してマシンでイベント ログとプロキシ設定を構成する](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [手順 4.Defender for Identity による他のコンピューター上のローカル管理者の識別を許可する](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a>手順 1。 Defender for Identity Instance を設定する

Defender for Identity ポータルにサインインしてインスタンスを作成し、このインスタンスを Active Directory 環境に接続します。 

|  手順 | 説明     |詳細情報  |
|---------|---------|---------|
|1     | Defender for Identity インスタンスを作成する        | [クイックスタート: Microsoft Defender for Identity インスタンスを作成する](/defender-for-identity/install-step1)        |
|2     | Defender for Identity インスタンスを Active Directory フォレストに接続する   | [クイック スタート: Active Directory フォレストに接続する](/defender-for-identity/install-step2)  |

## <a name="step-2-install-and-configure-the-sensor"></a>手順 2。 センサーをインストールして構成する

次に、オンプレミス環境のドメイン コントローラーと AD FS サーバーに Defender for Identity センサーをダウンロードしてインストールし、構成します。

|  手順 | 説明     |詳細情報  |
|---------|---------|---------|
|1     | 必要なMicrosoft Defender for Identityセンサーの数を決定します。        | [Microsoft Defender for Identity の容量を計画する](/defender-for-identity/capacity-planning)   |
|2     | センサーセットアップ パッケージをダウンロードする  |  [クイック スタート: Microsoft Defender for Identity センサーセットアップ パッケージをダウンロードする](/defender-for-identity/install-step3)   |
|3     | Defender for Identity センサーをインストールする    |  [クイック スタート: Microsoft Defender for Identity センサーをインストールする](/defender-for-identity/install-step4)       |
|4     | センサーを構成する       |  [Microsoft Defender for Identityセンサー設定を構成する](/defender-for-identity/install-step5)   |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a>手順 3. センサーを使用してマシンでイベント ログとプロキシ設定を構成する

センサーをインストールしたコンピューターで、検出機能を有効にして強化するように、Windows イベント ログ収集とインターネット プロキシ設定を構成します。

|  手順 | 説明     |詳細情報  |
|---------|---------|---------|
|1     | Windows イベント ログ収集を構成する         | [Windows イベント コレクションを構成する](/defender-for-identity/configure-windows-event-collection)        |
|2     | インターネット プロキシ設定を構成する        | [Microsoft Defender for Identity センサーのエンドポイント プロキシとインターネット接続の設定を構成する](/defender-for-identity/configure-proxy)        |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a>手順 4. Defender for Identity による他のコンピューター上のローカル管理者の識別を許可する

横移動パスの検出Microsoft Defender for Identityは、特定のマシン上のローカル管理者を識別するクエリに依存します。 これらのクエリは、Defender for Identity Service アカウントを使用して SAM-R プロトコルで実行されます。 

Windows クライアントとサーバーで Defender for Identity アカウントによる SAM-R の実行を許可するには、ネットワーク アクセス ポリシーに記載されている構成済みアカウントに加えて、Defender for Identity サービス アカウントを追加するグループ ポリシーを変更する必要があります。 **ドメイン コントローラーを除く** すべてのコンピューターにグループ ポリシーを適用してください。

これを行う方法については、「[SAM へのリモート呼び出しを行うMicrosoft Defender for Identityを構成する」を](/defender-for-identity/install-step8-samr)参照してください。 

## <a name="next-steps"></a>次の手順

手順 3/3: [パイロット Microsoft Defender for Identity](eval-defender-identity-pilot.md)

[Microsoft Defender for Identityの評価](eval-defender-identity-overview.md)の概要に戻る

[評価とパイロットのMicrosoft 365 Defender](eval-overview.md)の概要に戻る
