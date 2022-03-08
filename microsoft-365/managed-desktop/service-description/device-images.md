---
title: デバイスの画像
description: 新しいデバイスを注文する場合、または既存のデバイスを再利用する場合のイメージ要件
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: f1d00c12512b70ffd62372aaeae787acf1911573
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330287"
---
# <a name="device-images"></a>デバイスの画像

新しい[デバイスを注文](#new-devices)する場合でも[](#existing-devices)、既存のデバイスを再利用する場合でも、デバイス上のイメージがデバイス要件を満たしていることを確認するためのいくつかのオプション[があります](device-requirements.md#check-hardware-requirements)。

## <a name="new-devices"></a>新しいデバイス

承認された製造元から新しいデバイスを[](device-requirements.md#minimum-requirements)注文する場合は、次の手順に従って、適切な Microsoft Managed Desktop イメージとソフトウェア構成でデバイスを出荷します。

サービスに初めて特定のデバイス モデルを登録する予定がある場合は、そのモデルが期待するユーザー エクスペリエンスを確実に提供するための例をテストする必要があります。 詳細については、「新しいデバイスの [検証」を参照してください](/microsoft-365/managed-desktop/get-started/validate-device)。

### <a name="dell"></a>Dell

Dell の営業担当者と直接お問い合わせください。

代理人は、Microsoft Managed Desktop によって承認されたイメージが、ご注文のデバイスに適用されます。 Dell デバイス、イメージ、並べ替えプロセスの詳細については、お問い合 MMD_at_dell@dell.com。

### <a name="hp"></a>HP

HP から新しいデバイスを注文する場合は、[ビジネス デバイスの購入] ページにある各モデルの [追加要件] セクションに記載されている特定の SKU をWindows Pro[してください](https://www.microsoft.com/windows/business/devices#view-all-filter)。 ビューをフィルター処理して、Microsoft 管理デスクトップ デバイスを一覧表示します。

例外として承認されているが、現在 [デバイス一覧] ページに表示されていない [](customizing.md)HP からデバイスを注文する場合は、モデルに使用する SKU を要求します。 例外要求を使用してこの情報を取得するために HP と作業します。 次のアドレスを使用して、デバイスとデバイスの順序付け手順に関する質問については、HP に直接お問い合わせください。

- 南北アメリカ: mmd-americas@hp.com
- ヨーロッパ/中東/アフリカ: mmd-emea@hp.com
- アジア太平洋/日本: mmd-apj@hp.com
- グローバル: mmd@hp.com

### <a name="lenovo"></a>Lenovo

Lenovo からデバイスを注文する場合は、その順序で特定のパーツ番号を指定する必要があります。 Lenovo の営業担当者または Lenovo チャネル パートナーに問い合わせて、デバイス要件を満たすシステムを使用して"特別入札 *モデル" を* 作成 [してください。](device-requirements.md#minimum-requirements)

Microsoft Managed Desktop と互換性のある事前読み込みイメージを含めるには、営業担当者に「システム構築ブロックパーツ番号 *SBB0Q94938 - MMD Enablement*」を参照してください。 推奨されるサービス、サポート、イメージング サービスについては、Lenovo 営業担当者または Lenovo チャネル パートナーと一緒に作業してください。

### <a name="microsoft"></a>Microsoft

デバイス要件を満たすすべての Microsoft デバイスには、Microsoft Managed Desktop で動作するイメージが用意されています。 他の手順は必要ありません。

Microsoft デバイスのファクトリで利用可能な最新のイメージを取得するには、Surface スペシャリストと一緒に Surface "Pegged PO" プロセスを使用します。

## <a name="existing-devices"></a>既存のデバイス

既存のデバイスは、次の両方を満たす限り再利用できます。

- [デバイスの要件](device-requirements.md#minimum-requirements)
- [ソフトウェア要件](device-requirements.md#installed-software)

製造元に関連する手順に従います。

デバイスは、製造元のイメージを使用するか、Microsoft Managed Desktop "ユニバーサル イメージ" を使用して再イメージ化できます。 適切な製造元イメージを取得するには、再利用する [モデルの新](#new-devices) しいデバイスを少なくとも 1 つ注文します。 次に、そのデバイスからイメージを取得し、まったく同じモデルの他のデバイスに適用できます。

> [!NOTE]
> イメージの作成、テスト、展開は、ユーザーが責任を負います。 また、カスタム イメージの代わりに可能な限り、製造元が提供する適切な画像を使用することをお勧めします。これには、"ユニバーサル イメージ" が含まれます。

### <a name="hp"></a>HP

HP Corporate Ready Image に同梱されている HP 商用 PC には、回復用の `.WIM` ファイルが含まれます。 このイメージを使用して、工場出荷時の復元イメージを同じモデルの他のデバイスに適用できます。

次の手順では、デバイス上のすべてのデータを削除します。 開始する前に、保持するデータをバックアップする必要があります。

**デバイス上のデータを削除するには、次の方法を実行します。**

1. WinPE [を使用して起動可能な USB ドライブ](/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive)を作成します。
2. 次のファイルを `C:\\SOURCES` USB ドライブにコピーします。
    - 工場出荷時の回復 WIM ファイル (たとえば) `HP\_EliteBook\_840\_G7\_Notebook\_PC\_CR\_2004.wim`
    - `DEPLOY.CMD`
    - `ReCreatePartitions.txt`
3. [WinPE にデバイスを起動する](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) USB ドライブ。
4. コマンド プロンプトで、次のコマンド [ をDiskpart.exe](/windows-server/administration/windows-commands/diskpart#additional-references)。
5. Diskpart で、実行し `list disk`、プライマリ 記憶域ディスク番号 (通常はディスク 0) をメモします。
6. 入力して Diskpart を終了します `exit`。
7. コマンド プロンプトで、決定`deploy.cmd <sys_disk> <recovery_wim>``sys_disk` `recovery_wim` `.WIM`したプライマリ ストレージ ディスクのディスク番号と、前にコピーしたファイルのファイル名を指定します。
8. USB ドライブを取り外し、デバイスを再起動します。

### <a name="microsoft"></a>Microsoft

Microsoft Surface デバイスには、各モデルに固有の "ベア メタル [回復" イメージ](https://support.microsoft.com/en-us/surfacerecoveryimage) が含まれます。 これらのイメージを使用してデバイスを再イメージ化できます。

これらのイメージは、回復Windows (WinRE) を使用します。 これは手動プロセスです (自動化されません)。 「Surface の USB 回復ドライブ [を作成して使用する」の手順に従います](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07)。

### <a name="universal-image"></a>ユニバーサル イメージ

Microsoft Managed Desktop では、Microsoft 管理デスクトップで使用Windows Pro、Microsoft 365 AppsのEnterpriseを含むイメージが作成されました。

ただし、ユーザーがサインインした後に古い Windows バージョンを更新する必要がある場合でも、可能な限り、製造元が提供する Microsoft Managed Desktop に適したイメージを使用してください。 Microsoft Managed Desktop Universal イメージの使用は、最終的なオプションである必要があります。

- 30 ~ 60 日ごとに最新の Windows の品質更新プログラムを使用し、少なくとも年に 2 回は Microsoft 365 Apps Enterprise 更新プログラムで画像を更新します。
- イメージには、回復のシナリオに従ってMicrosoft 365 Apps Enterprise復元するための回復Windowsパッケージが含まれています。
- USB ドライブを使用してイメージを展開できます。 ドライバーを挿入するスクリプト可能なプロセスが含まれている。 このプロセスの概要は、イメージに含まれるドキュメントに示されています。
- 含まれているスクリプトとフォルダーは、特定の累積的な更新プログラムの追加、ファイル コピー コードの追加、その他のチェックの実行など、他のカスタマイズを使用して変更できます。
- ドライバーと品質更新プログラムは、USB ドライブからのWindowsに追加されます。

> [!NOTE]
> 必要なすべてのドライバーを追加し、すべてのテストを実行し、最終的に展開されたイメージに問題が発生しなかからず確認する必要があります。 ユニバーサル イメージは"as-is" で提供されますが、技術的なガイダンスを提供し、質問に答えます。 連絡先 MMDImage@microsoft.com。

変更要求を作成して、ユニバーサル イメージのコンテンツとドキュメントの要求を管理者ポータル [に送信します](../get-started/access-admin-portal.md)。
