---
title: グループ ポリシーを使用してウイルス対策スキャンをスケジュールする
description: グループ ポリシーを使用してウイルス対策スキャンをセットアップする
keywords: クイック スキャン、フル スキャン、スケジュール、グループ ポリシー、ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/13/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: f59c91e75dd573e9f32d05a9673dd3efb5c10af7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191704"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a>グループ ポリシーを使用してウイルス対策スキャンをスケジュールする

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

この記事では、グループ ポリシーを使用してスケジュールされたスキャンを構成する方法について説明します。 スキャンのスケジュール設定とスキャンの種類の詳細については、「スケジュールされたクイック スキャンまたはフル スキャンの構成[」をMicrosoft Defender ウイルス対策してください](schedule-antivirus-scans.md)。 

## <a name="configure-antivirus-scans-using-group-policy"></a>グループ ポリシーを使用してウイルス対策スキャンを構成する

1. グループ ポリシー管理マシンのグループ ポリシー エディターで、[コンピューター構成] [管理用テンプレート] Windows [スキャンMicrosoft Defender ウイルス対策 \>  \>  \>  \> **します**。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。

3. グループ ポリシー オブジェクトの設定を指定し **、[OK] を選択します**。 

4. 構成する設定ごとに手順 1 ~ 4 を繰り返します。

5. 通常と同じ方法でグループ ポリシー オブジェクトを展開します。 グループ ポリシー オブジェクトのヘルプが必要な場合は、「 [グループ ポリシー オブジェクトの作成」を参照してください](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)。

> [!NOTE]
> スケジュールされたスキャンを構成する場合、既定で有効になっているコンピューターがオンになっているが使用されていない場合にのみ、スケジュールされたスキャンを開始する設定は、コンピューターを最初にアイドル状態にすることで、予期されるスケジュールされた時間に影響を与える可能性があります。
>
> 毎週のスキャンの場合、Windows サーバーの既定の動作は、コンピューターがアイドル状態のときに自動メンテナンスの外部でスキャンします。 コンピューターがアイドル状態Windows 10、コンピューターの自動メンテナンス中にスキャンが実行されます。 この動作を変更するには **、ScanOnlyIfIdle** を無効にして設定を変更し、スケジュールを定義します。

詳細については、「保護更新プログラム [をダウンロードして](manage-protection-update-schedule-microsoft-defender-antivirus.md) 適用する必要がある場合の管理」および「ユーザーによるポリシー設定のローカル変更を防止または許可する」 [のトピックを参照](configure-local-policy-overrides-microsoft-defender-antivirus.md) してください。

## <a name="group-policy-settings-for-scheduling-scans"></a>スキャンのスケジュール設定のグループ ポリシー設定

| Location | Setting | 説明 | 既定の設定 (構成されていない場合) |
|:---|:---|:---|:---|
| スキャン | スケジュールされたスキャンに使用するスキャンの種類を指定する | クイック スキャン |
| スキャン | スケジュールされたスキャンを実行する週の日を指定する | スキャンを実行する日 (または実行しない) を指定します。 | Never |
| スキャン | スケジュールされたスキャンを実行する時刻を指定する | 午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。 | 2 a.m. |
| ルート | スケジュールされたタスク時間をランダム化する |このMicrosoft Defender ウイルス対策、スキャンの開始時刻を 0 ~ 4 時間の任意の間隔にランダム化します。 <p>[SCEP では](/mem/intune/protect/certificates-scep-configure)、スキャンを任意の間隔にプラスまたはマイナス 30 分にランダム化します。 これは、仮想マシンまたは VDI 展開で役立ちます。 | Enabled |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a>エンドポイントが使用されていないときにスキャンをスケジュールするグループ ポリシー設定

| Location | Setting | 説明 | 既定の設定 (構成されていない場合) |
|:---|:---|:---|:---|
| スキャン | コンピューターがオンで、使用されていない場合にのみ、スケジュールされたスキャンを開始する | コンピューターがオンで使用されていない場合、スケジュールされたスキャンは実行されません。 | Enabled |

> [!NOTE]
> エンドポイントが使用されていない時間のスキャンをスケジュールする場合、スキャンは CPU 調整構成を尊重し、可能な限り高速にスキャンを完了するために利用可能なリソースを活用します。

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a>修復に必要なスキャンをスケジュールするためのグループ ポリシー設定

| Location | Setting | 説明 | 既定の設定 (構成されていない場合) |
|---|---|---|---|
| 修復 | スケジュールされたフル スキャンを実行して修復を完了する日を指定する | スキャンを実行する日 (または実行しない) を指定します。 | Never |
| 修復 | スケジュールされたフル スキャンを実行して修復を完了する時刻を指定する | 午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。 | 2 a.m. |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a>毎日のスキャンをスケジュールするグループ ポリシー設定

| Location | Setting | 説明 | 既定の設定 (構成されていない場合) |
|:---|:---|:---|:---|
| スキャン | 1 日あたりのクイック スキャンを実行する間隔を指定する | 次のクイック スキャンの前に経過する時間を指定します。 たとえば、2 時間ごとに実行するには **、「2」と入力し、1** 日 1 回は **24 と入力します**。 **0 と入力** すると、毎日のクイック スキャンは実行されません。 | Never |
| スキャン | 毎日のクイック スキャンの時間を指定する | 午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。 | 2 a.m. |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a>保護更新後にスキャンをスケジュールするグループ ポリシー設定

| Location | Setting | 説明 | 既定の設定 (構成されていない場合)|
|:---|:---|:---|:---|
| 署名の更新 | セキュリティ インテリジェンスの更新後にスキャンを有効にする | 新しい保護更新プログラムがダウンロードされた直後にスキャンが実行されます | Enabled |

