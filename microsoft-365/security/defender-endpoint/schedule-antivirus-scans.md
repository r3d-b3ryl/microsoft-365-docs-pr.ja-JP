---
title: Microsoft Defender ウイルス対策を使用して定期的なクイック スキャンとフル スキャンをスケジュールする
description: 定期的な (スケジュールされた) スキャンをセットアップする (実行するタイミングや、フル スキャンとクイック スキャンのどちらで実行するかなど)
keywords: クイック スキャン, フル スキャン、クイックとフル、スキャンのスケジュール、毎日、毎週、時間、スケジュール、定期的、定期的
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 02/22/2022
ms.reviewer: pauhijbr, ksarens, mkaminska
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: e7b854b2a4c9f4202296ed404d067182de8627bd
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790265"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>スケジュールされたクイックまたは完全な Microsoft Defender ウイルス スキャンを構成する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

常時オン、リアルタイムの保護、[オンデマンドのウイルス対策](run-scan-microsoft-defender-antivirus.md)スキャンに加えて、定期的にスケジュールされたウイルス対策スキャンを設定できます。 スキャンの種類、スキャンが行われるタイミング、および [保護の更新](manage-protection-updates-microsoft-defender-antivirus.md)後にスキャンを実行するかどうか、またはエンドポイントが使用されていないときにスキャンを実行するかどうかを構成できます。 必要に応じて、修復アクションを完了するように特別なスキャンを設定することもできます。

## <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください

- [クイック スキャン、フル スキャン、カスタム スキャンの詳細情報](#quick-scan-full-scan-and-custom-scan)
- [グループ ポリシーを使用してウイルス対策スキャンをスケジュールする](schedule-antivirus-scans-group-policy.md)
- [Windows PowerShell を使用してウイルス対策スキャンをスケジュールする](schedule-antivirus-scans-powershell.md)
- [Windows Management Instrumentation を使用してウイルス対策スキャンをスケジュールする](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a>以下の点にご注意ください。

- 既定では、Microsoft Defender ウイルス対策は、スケジュールされたスキャンの時刻の 15 分前に更新プログラムを確認します。 [保護更新プログラムをダウンロードして適用する必要がある場合のスケジュールを管理](manage-protection-update-schedule-microsoft-defender-antivirus.md)して、この既定値をオーバーライドできます。

- スケジュールされたフル スキャン中にデバイスが取り外され、バッテリで実行されている場合、スケジュールされたスキャンはイベント 1002 で停止します。これは、スキャンが完了する前に停止したことを示します。 Microsoft Defender ウイルス対策は、次回のスケジュールされた時刻にフル スキャンを実行します。

## <a name="quick-scan-full-scan-and-custom-scan"></a>クイック スキャン、フル スキャン、カスタム スキャン

スケジュールされたスキャンを設定するときに、スキャンをフル スキャンとクイック スキャンのどちらにするかを指定できます。 ほとんどの場合、クイック スキャンをお勧めします。

<br/><br/>

|クイック スキャン|フル スキャン|カスタム スキャン|
|---|---|---|
|(推奨) クイック スキャンでは、レジストリ キーや既知の Windows スタートアップ フォルダーなど、システムで起動するためにマルウェアが登録されている可能性があるすべての場所を調べます。 <br/><br/>常時オンのリアルタイム保護と組み合わせることで、ファイルを開いたり閉じたりしたときにファイルを確認したり、ユーザーがフォルダーに移動するたびに、クイック スキャンを使用して、システムやカーネル レベルのマルウェアから始まるマルウェアに対する強力な保護を提供できます。<br/><br/>ほとんどの場合、クイック スキャンで十分であり、スケジュールされたスキャンに推奨されるオプションとなっています。|フル スキャンは、クイック スキャンを実行することから始まり、マウントされているすべての固定ディスクとリムーバブル/ネットワーク ドライブの順次ファイル スキャンを続行します (フル スキャンがそのように構成されている場合)。<br/><br/>フル スキャンは、スキャンする必要があるデータの量と種類に応じて、完了までに数時間または数日かかることがあります。<br/><br/>フル スキャンが完了すると、新しいセキュリティ インテリジェンスが使用可能になり、新しいセキュリティ インテリジェンスで他の脅威が検出されていないことを確認するために新しいスキャンが必要になります。<br/><br/>フル スキャンには時間とリソースが関係するため、通常、Microsoft ではフル スキャンのスケジュールを設定することはお勧めしません。|カスタム スキャンは、指定したファイルとフォルダーで実行されます。 たとえば、USB ドライブ、またはデバイスのローカル ドライブ上の特定のフォルダーをスキャンすることを選択できます。|

> [!NOTE]
> 既定では、USB ドライブなどのマウントされたリムーバブル デバイスでクイック スキャンが実行されます。

## <a name="how-do-i-know-which-scan-type-to-choose"></a>選択するスキャンの種類を知るにはどうすればいいですか?

次の表を使用して、スキャンの種類を選択します。
<br/><br/>

|シナリオ|推奨されるスキャンの種類|
|---|---|
|定期的なスケジュールされたスキャンを設定する場合|クイック スキャン <p> クイック スキャンでは、デバイス上のプロセス、メモリ、プロファイル、および特定の場所がチェックされます。 [常時オンのリアルタイム保護](configure-real-time-protection-microsoft-defender-antivirus.md)と組み合わせることで、クイック スキャンを使用すると、システムから始まるマルウェアとカーネル レベルのマルウェアの両方に強力なカバレッジを提供できます。 リアルタイム保護は、ファイルを開いたり閉じたり、ユーザーがフォルダーに移動するたびにファイルをレビューします。|
|マルウェアなどの脅威が個々のデバイスで検出される|クイック スキャン <p> ほとんどの場合、クイック スキャンは検出されたマルウェアをキャッチしてクリーンアップします。|
|[オンデマンド スキャン](run-scan-microsoft-defender-antivirus.md)を実行する場合|クイック スキャン|
|USB ドライブなどのポータブル デバイスにマルウェアが含まれていないことを確認する必要がある|カスタム スキャン <p> カスタム スキャンを使用すると、特定の場所、フォルダー、またはファイルを選択し、クイック スキャンを実行できます。|

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>クイック スキャンとフル スキャンについて他にも知る必要のあることがありますか?

- 悪意のあるファイルは、クイック スキャンに含まれていない場所に格納される可能性があります。 ただし、常時オンのリアルタイム保護では、開かれたファイルと閉じられているすべてのファイル、およびユーザーがアクセスするフォルダー内のすべてのファイルが確認されます。 リアルタイム保護とクイック スキャンの組み合わせは、マルウェアに対する強力な保護を提供するのに役立ちます。

- [クラウドで提供される保護](cloud-protection-microsoft-defender-antivirus.md)を使用したオンアクセス保護は、システム上でアクセスされるすべてのファイルが最新のセキュリティ インテリジェンスとクラウド機械学習モデルを使用してスキャンされていることを確認するのに役立ちます。

- リアルタイム保護によってマルウェアが検出され、影響を受けるファイルの範囲が最初に決定されない場合、Microsoft Defender ウイルス対策は修復プロセスの一環としてフル スキャンを開始します。

- フル スキャンでは、クイック スキャンなど、他のスキャンで検出されなかった悪意のあるファイルを検出できます。 ただし、フル スキャンには時間がかかり、重要なシステム リソースを使用して完了できます。

- デバイスが長時間オフラインの場合、フル スキャンが完了するまでに時間がかかる場合があります。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)