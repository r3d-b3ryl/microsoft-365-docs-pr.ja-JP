---
title: グループ ポリシーを使用してウイルス対策スキャンをスケジュールする
description: グループ ポリシーを使用してウイルス対策スキャンを設定する
keywords: クイック スキャン, フル スキャン, スケジュール, グループ ポリシー, ウイルス対策
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/10/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: dbd3f2b4342757509a6440ff87a112b75b663f22
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788042"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a>グループ ポリシーを使用してウイルス対策スキャンをスケジュールする

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

この記事では、グループ ポリシーを使用してスケジュールされたスキャンを構成する方法について説明します。 スキャンのスケジュール設定とスキャンの種類の詳細については、「[スケジュールされたクイック スキャンまたはフル Microsoft Defender ウイルス対策 スキャンの構成](schedule-antivirus-scans.md)」を参照してください。 

## <a name="configure-antivirus-scans-using-group-policy"></a>グループ ポリシーを使用してウイルス対策スキャンを構成する

1. グループ ポリシー管理マシンのグループ ポリシー エディターで、[**コンピューター構成** \> **管理用テンプレート** \> **] Windows [コンポーネント** \> **Microsoft Defender ウイルス対策**\>スキャン] に移動 **します**。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

3. グループ ポリシー オブジェクトの設定を指定し、[OK] を選択 **します**。 

4. 構成する設定ごとに手順 1 ~ 4 を繰り返します。

5. 通常どおりに、グループ ポリシー オブジェクトをデプロイします。 グループ ポリシー オブジェクトに関するヘルプが必要な場合は、「[グループ ポリシー オブジェクトを作成する](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)」を参照してください。

> [!NOTE]
> スケジュールされたスキャンを構成するときに、[ **スケジュールされたスキャンを開始する] 設定は、コンピューターがオンになっているが、既定では有効になっていない場合にのみ**、コンピューターを最初にアイドル状態にする必要があるため、スケジュールされた時刻に影響を与える可能性があります。
>
> 毎週のスキャンの場合、Windows サーバーでの既定の動作は、マシンがアイドル状態のときに自動メンテナンスの外部でスキャンすることです。 Windows 10 以降の既定値は、マシンがアイドル状態のときに自動メンテナンス中にスキャンすることです。 この動作を変更するには、 **ScanOnlyIfIdle** を無効にして設定を変更し、スケジュールを定義します。

詳細については、「 [保護更新プログラムをダウンロードして適用する必要がある場合の管理」と](manage-protection-update-schedule-microsoft-defender-antivirus.md) 「 [ユーザーがポリシー設定をローカルで変更できないようにする、または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md) 」トピックを参照してください。

## <a name="group-policy-settings-for-scheduling-scans"></a>スキャンのスケジュール設定をグループ ポリシーする

| 場所 | 設定 | 説明 | 既定の設定 (構成されていない場合) |
|:---|:---|:---|:---|
| スキャン | スケジュールされたスキャンに使用するスキャンの種類を指定する | クイック スキャン |
| スキャン | スケジュールされたスキャンを実行する曜日を指定する | スキャンを実行する日 (または実行しない) を指定します。 | Never |
| スキャン | スケジュールされたスキャンを実行する時刻を指定する | 午前 0 時以降の分数を指定します (たとえば、午前 1 時に **60** と入力します)。 | 午前 2 時 |
| ルート | スケジュールされたタスク時間をランダム化する |Microsoft Defender ウイルス対策では、スキャンの開始時刻を 0 ~ 23 時間の任意の間隔にランダム化します。 <p>[SCEP](/mem/intune/protect/certificates-scep-configure) では、スキャンを任意の間隔 (プラスマイナス 30 分) にランダム化します。 これは、仮想マシンまたは VDI のデプロイに役立ちます。 | Enabled |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a>エンドポイントが使用されていない場合のスキャンのスケジュール設定をグループ ポリシーする

| 場所 | 設定 | 説明 | 既定の設定 (構成されていない場合) |
|:---|:---|:---|:---|
| スキャン | コンピューターがオンになっていて使用中でない場合にのみ、スケジュールされたスキャンを開始する | コンピューターがオンになっているが使用中でない場合を除き、スケジュールされたスキャンは実行されません | Enabled |

> [!NOTE]
> エンドポイントが使用されていない時間にスキャンをスケジュールすると、スキャンは CPU 調整構成を受け入れず、使用可能なリソースを最大限に活用して、できるだけ早くスキャンを完了します。

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a>修復に必要なスキャンをスケジュールするためのグループ ポリシー設定

| 場所 | 設定 | 説明 | 既定の設定 (構成されていない場合) |
|---|---|---|---|
| 修復 | スケジュールされたフル スキャンを実行して修復を完了する曜日を指定する | スキャンを実行する日 (または実行しない) を指定します。 | Never |
| 修復 | スケジュールされたフル スキャンを実行して修復を完了する時刻を指定する | 午前 0 時以降の分数を指定します (たとえば、午前 1 時に **60** と入力します)。 | 午前 2 時 |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a>毎日のスキャンをスケジュールするためのグループ ポリシー設定

| 場所 | 設定 | 説明 | 既定の設定 (構成されていない場合) |
|:---|:---|:---|:---|
| スキャン | 1 日あたりのクイック スキャンを実行する間隔を指定する | 次のクイック スキャンの前に経過する時間を指定します。 たとえば、2 時間ごとに実行するには **、「2**」と入力し、1 日に 1 回は **「24**」と入力します。 毎日のクイック スキャンを実行しない場合は **、0** と入力します。 | Never |
| スキャン | 1 日のクイック スキャンの時間を指定する | 午前 0 時以降の分数を指定します (たとえば、午前 1 時に **60** と入力します)。 | 午前 2 時 |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a>保護の更新後にスキャンをスケジュールするためのグループ ポリシー設定

| 場所 | 設定 | 説明 | 既定の設定 (構成されていない場合)|
|:---|:---|:---|:---|
| 署名の更新 | セキュリティ インテリジェンスの更新後にスキャンを有効にする | 新しい保護更新プログラムがダウンロードされた直後にスキャンが行われます | Enabled |

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS でMicrosoft Defender for Endpointの基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [IntuneのMicrosoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux でMicrosoft Defender for Endpointの基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android の機能で Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)