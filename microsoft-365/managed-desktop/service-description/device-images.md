---
title: デバイスの画像
description: 新しいデバイスを注文する場合、または既存のデバイスを再利用する場合のイメージ要件
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 8b8b1647fec96dd43ab5ed57c324d4e1525af0c377d8757034b6171dc606107d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53863885"
---
# <a name="device-images"></a>デバイスの画像


新しい[デバイスを注文](#new-devices)する場合でも[](#existing-devices)、既存のデバイスを再利用する場合でも、デバイス上のイメージがデバイス要件を満たしていることを確認するためのいくつかのオプション[があります](device-requirements.md#check-hardware-requirements)。

## <a name="new-devices"></a>新しいデバイス
承認された製造元から新しいデバイスを[](device-requirements.md#minimum-requirements)注文する場合は、次の手順に従って、デバイスに適切なイメージとソフトウェア構成をMicrosoft マネージド デスクトップしてください。 サービスに初めて特定のデバイス モデルを登録する予定がある場合は、そのモデルが期待するユーザー エクスペリエンスを提供するための例をテストする必要があります。 詳細については、「新しいデバイスの [検証」を参照してください](/microsoft-365/managed-desktop/get-started/validate-device)。

### <a name="dell"></a>Dell
Dell の営業担当者と直接連絡を取り合い、ユーザーが承認した画像がMicrosoft マネージド デスクトップデバイスに適用されます。 Dell デバイス、イメージ、および注文プロセスに関する詳細な質問については、次の MMD_at_dell@dell.com。

### <a name="hp"></a>HP 
HP から新しいデバイスを注文する場合は、ショップ[Windows 10 Pro](https://www.microsoft.com/windowsforbusiness/view-all-devices#view-all-filter)ビジネス デバイス サイトにある各モデルの [追加要件] セクションに記載されている特定の SKU を必ず使用してください (Microsoft マネージド デスクトップ デバイスを表示するためにビューをフィルター処理します)。

例外として承認されているが、現在 [デバイス一覧] ページに[](customizing.md)表示されていない HP からデバイスを注文する場合は、必ずモデルに使用する SKU を要求してください。 例外要求を使用してこの情報を取得するために HP と作業します。 次のアドレスを使用して、デバイスとデバイスの順序付け手順に関する質問については、HP に直接お問い合わせください。
 
- 南北アメリカ: mmd-americas@hp.com
- ヨーロッパ/中東/アフリカ: mmd-emea@hp.com
- アジア太平洋/日本: mmd-apj@hp.com
- グローバル: mmd@hp.com

### <a name="lenovo"></a>Lenovo
Lenovo からデバイスを注文して、Microsoft マネージド デスクトップで使用する場合は、注文の一部として含まれる特定のパーツ番号を指定する必要があります。 Lenovo の営業担当者または Lenovo チャネル パートナーに問い合わせて、デバイス要件を満たすシステムを使用して"特別入札 *モデル"* を作成 [してください。](device-requirements.md#minimum-requirements) Microsoft マネージド デスクトップ と互換性のある事前に読み込まれたイメージを含めるには、営業担当者に「システム構築ブロックのパーツ番号 *SBB0Q94938 – MMD Enablement*」を参照してください。 推奨されるサービス、サポート、イメージング サービスについては、Lenovo 営業担当者または Lenovo チャネル パートナーと一緒に作業してください。

### <a name="microsoft"></a>Microsoft
デバイス要件を満たすすべての Microsoft デバイスには、デバイスに対応するイメージMicrosoft マネージド デスクトップ。 他の手順は必要ありません。

Microsoft デバイスのファクトリで利用可能な最新のイメージを取得するには、Surface スペシャリストと一緒に Surface "Pegged PO" プロセスを使用します。

## <a name="existing-devices"></a>既存のデバイス

既存のデバイスは、デバイス要件とソフトウェア要件の両方を[](device-requirements.md#minimum-requirements)満たしている限り[再利用できます](device-requirements.md#installed-software)。 製造元に関連する手順に従います。

デバイスは、製造元のイメージを使用するか、"ユニバーサル イメージ" を使用Microsoft マネージド デスクトップイメージを再作成できます。 適切な製造元イメージを取得するには、再利用するモデルの新[](#new-devices)しいデバイスを少なくとも 1 つ注文できます。 その後、そのデバイスからイメージを取得し、まったく同じモデルの他のデバイスに適用できます。

> [!NOTE]
> イメージの作成、テスト、展開は、ユーザーが責任を負います。 また、カスタム イメージ ("ユニバーサル イメージ" を含む) の代わりに、可能な限り製造元が提供する適切な画像を使用することをお勧めします。

### <a name="hp"></a>HP

HP Corporate Ready Image に同梱されている HP 商用 PC には、 が含まれます。回復用の WIM ファイル。 このイメージを使用して、工場出荷時の復元イメージを同じモデルの他のデバイスに適用できます。

これらの手順では、デバイス上のすべてのデータが削除されます。そのため、開始する前に、保持するデータをバックアップする必要があります。

1. WinPE[を使用して起動可能な USB ドライブ](/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive)を作成します。
2. C: SOURCES から \\ USB ドライブにこれらのファイルをコピーします。
    - 工場出荷時の回復 WIM ファイル (HP \_ EliteBook \_ 840 \_ G7 \_ ノートブック PC CR \_ \_ \_ 2004.wim など)
    - DEPLOY。CMD
    - ReCreatePartitions.txt
3. [WinPE にデバイスを起動する](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) USB ドライブ。
4. コマンド プロンプトで、次のコマンド[をDiskpart.exe。 ](/windows-server/administration/windows-commands/diskpart#additional-references)
5. Diskpart で、実行し、プライマリ 記憶域ディスク番号 (通常はディスク `list disk` 0) をメモします。
6. 入力して Diskpart を終了 `exit` します。
7. コマンド プロンプトで、 を実行します。sys_disk は、決定したプライマリ ストレージ ディスクのディスク番号であり、recovery_wim ファイル名です `deploy.cmd <sys_disk> <recovery_wim>` 。  前にコピーした WIM ファイル。
8. USB ドライブを取り外し、デバイスを再起動します。

### <a name="microsoft"></a>Microsoft 

Microsoft Surface デバイスには、各モデルに固有の "ベア メタル [回復"](https://support.microsoft.com/en-us/surfacerecoveryimage) イメージが含まれます。 これらのイメージを使用してデバイスを再イメージ化できます。

これらのイメージは、Windows回復環境 (WinRE) を使用します。これは手動プロセスです (自動化されません)。 「Surface の USB 回復ドライブ [を作成して使用する」の手順に従います](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07)。


### <a name="universal-image"></a>ユニバーサル イメージ
Microsoft マネージド デスクトップで使用できる、Windows 10 ProとMicrosoft 365 Apps Enterpriseを含むイメージがMicrosoft マネージド デスクトップ。 ただし、ユーザーがサインインしたら更新する必要がある古い Windows バージョンを意味する場合でも、可能な限り、製造元が提供する Microsoft マネージド デスクトップ に適した画像を使用してください。 ユニバーサル イメージをMicrosoft マネージド デスクトップ、最終的なオプションにする必要があります。

- 30~ 60 日ごとに最新のWindows品質更新プログラムを使用して画像を更新し、Microsoft 365 Apps Enterprise更新プログラムを少なくとも年に 2 回更新します。
- イメージには、回復のシナリオに従ってMicrosoft 365 Apps Enterprise復元するための回復Windowsパッケージが含まれています。
- USB ドライブを使用してイメージを展開できます。 ドライバーを挿入するスクリプト可能なプロセスが含まれています (イメージに含まれるドキュメントで説明されています)。
- 含まれているスクリプトとフォルダーは、特定の累積的な更新プログラムの追加、ファイル コピー コードの追加、その他のチェックの実行など、他のカスタマイズで使用するために変更できます。
- ドライバーと品質更新プログラムは、USB ドライブからのWindowsに追加されます。

> [!NOTE]
> 必要なすべてのドライバーを追加し、すべてのテストを実行し、最終的に展開されたイメージに問題が発生しなかからず確認する必要があります。 ユニバーサル イメージは"as-is" で提供されますが、技術的なガイダンスを提供し、質問に答えます。 連絡先 MMDImage@microsoft.com。

管理ポータルで変更要求を作成して、ユニバーサル イメージのコンテンツとドキュメントの要求を [送信します](../get-started/access-admin-portal.md)。


