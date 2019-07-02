---
title: Windows 7 から Windows 10 への手動アップグレード ガイド
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Windows 7 から Windows 10 への手動アップグレード ガイド。
ms.openlocfilehash: f148815a72c9315db2a6d55f7b8433cc9dddf448
ms.sourcegitcommit: 12c4d5444d6e0e8825fc85e3e8453fa376746495
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2019
ms.locfileid: "35395354"
---
# <a name="windows-7-to-windows-10-manual-upgrade-step-by-step-guide"></a>Windows 7 から Windows 10 への手動アップグレードの手順ガイド

この記事では、Windows 7 Enterprise を実行する PC を Windows 10 Enterprise に手動でアップグレードする手順について説明します。 Home や Professional などのその他のエディションの Windows 7 でも手順はほとんど同じですが、メディア作成ツールを使用して直接アップグレードすることもできます。 すべてのエディションの Windows 7 から Windows 10 へのアップグレードには、有効なプロダクトキーおよび元のエディションと一致するまたはそれより上級のエディションの Windows が必要です。たとえば、Windows 7 Professional は Windows 10 Pro にアップグレードできますが、Windows 10 Home にアップグレードすることはできません。 Windows 7 Ultimate の場合、Windows 10 Pro にアップグレードする必要があります。

## <a name="windows-10-upgrades-using-the-media-creation-tool-or-iso-files"></a>メディア作成ツールまたは ISO ファイルを使用した Windows 10 へのアップグレード

[メディア作成ツール](https://www.microsoft.com/en-us/software-download/windows10ISO)を使用すると、Windows 10 に直接アップグレードすることができます。このツールを使用して Windows 10 を ISO ファイルとしてダウンロードすることもできます。 現在のシステムが 32 と 64 ビットのどちらであるか、システムの既定の言語、および Windows 7 のエディション (例: Home、Professional、Enterprise) を確認する必要があります。 Windows 7 の場合、この情報は [コントロールパネル] \> [システムとセキュリティ] \> [システム] にあります。 メディア作成ツールは、アップグレード、インストール メディアの作成、または ISO ファイルのダウンロードについて Windows 10 Enterprise をサポートしていません。 Windows 7 Enterprise からアップグレードする場合は、Windows 10 Enterprise が必要です。

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-1.png)

Windows 7 Enterprise から Windows 10 Enterprise にアップグレードする場合は、使用する言語とアーキテクチャ (32 ビットまたは 64 ビット) 用の ISO ファイルを[ボリューム ライセンス サービス センター](https://www.microsoft.com/licensing/servicecenter/default.aspx)からダウンロードする必要があります。

ISO ファイルを使用してアップグレードを実行する場合は、ISO 内のファイルをローカル ファイル システムまたはリムーバブル ドライブのいずれかに展開する必要があります。また、ISO ファイルを DVD に書き込むこともできます。 Windows 8 またはそれ以降の PC を使用して ISO 内のインストール ファイルを展開し、これらのファイルをリムーバブル USB ストレージに保存するか、または [7zip](https://www.7-zip.org/) などのアプリケーションを使用して ISO ファイルのコンテンツを Windows 7 内のローカル ドライブ上のフォルダーに展開することができます。

Windows 7 内でインストール メディアが準備できたら、次に示すように setup.exe を実行して、アップグレードを開始できます。

**重要なヒント: アプリケーションとデータが Windows 10 に移行されるインプレース アップグレードの場合は、実行中の Windows 7 セッション内からプロセスを開始する必要があります。DVD または USB ドライブからインストール メディアを起動する方法の場合、アプリとファイルを引き継ぐオプションが提供されず、Windows 10 のクリーン インストールが実行されます。**

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-2.png)

Windows 10 セットアップでは、手順に沿ってインストールの案内が提供されます。最初の画面では、更新プログラム、ドライバー、およびオプション機能をダウンロードするためのオプションが表示されます。 アップグレードを正常に完了させるために、実行することをお勧めします。

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-3.png)

更新プログラムの適用が完了すると、Windows 10 セットアップは次のステップの [画像の選択] に移動します。 この画面では、お使いの Windows のエディションを選択する必要があります。 この場合、PC には Windows 7 Enterprise がインストールされているため、[Windows 10 Enterprise] を選択します。

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-4.png)

Windows 10 セットアップの次の画面では、該当する通知とライセンス条項が表示されます。 通知と条項を読んで理解したら、続行する場合は [同意する] をクリックし、キャンセルする場合は [拒否する] をクリックします。

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-5.png)

Windows 10 セットアップは、その他の更新プログラムを探します。

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-6.png)

完了すると、Windows 10 セットアップでインストールを開始できる状態になります。既定では、Windows 10 がインストールされ、個人用のファイルとインストール済みのアプリが引き継がれる設定になっています。 これは推奨されるオプションです。 [引き継ぐものを変更] をクリックすると、追加のオプションが表示されます。 変更しない場合は、[インストール] をクリックします。

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-7.png)

[引き継ぐものを変更] を選択すると、次のオプションが表示されます。

[個人用ファイルのみを引き継ぐ] を選択した場合、インストールされているアプリまたは設定は Windows 7 から Windows 10 に移動されません。 代わりに、ファイルとユーザー アカウントのみが Windows に移動されます。 このオプションを使用する場合、アプリを後から再インストールする必要があります。 このオプションは、Windows のインストール後に必要なアプリの再インストールおよび構成を確実に行える場合にのみ選びます。それ以外の場合、既定のオプション [個人用ファイルとアプリを引き継ぐ] を使用するようにします。

[何もしない] を選択した場合、ファイル、アプリ、および設定は削除され、Windows のクリーン インストールが実行されます。 このオプションは、保持する必要があるデータを既にバックアップしてあり、アプリを再インストールできる場合にのみ使用します。

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-8.png)

Windows 10 セットアップでは、前の画面で選択した内容に基づいて更新プログラムが再びダウンロードされます。

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-9.png)

Windows 10 のインストールが開始し、完了するまで数分間かかります。個人用ファイルとアプリを引き継ぐオプションを選択した場合、すべてのファイルが以前と同じ場所に保存され、アプリは Windows 10 で利用できるようになります。

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-10.png)

## 

## <a name="recovery-in-windows-10"></a>Windows 10 の回復

Windows 10 のインストール後、Windows 10 の回復オプションを使用すると 10 日以内であれば Windows 7 に戻すことができます。 この機能は、システム上のデバイスやアプリが正常に機能しないために以前の Windows 7 のインストールに戻す必要がある場合に役立ちます。 10 日が経過すると、Windows 10 は Windows 7 の回復ファイルがハード ドライブで使用している領域を解放し、以前のインストールからのファイルを削除します。 この期間を過ぎると Windows 7 は削除され、Windows 7 に戻すことはできなくなりますが、アプリと個人用ファイルは Windows 10 に残ります。

[Windows 7 に戻す] プロセスを開始するには、[設定]　 \> [更新とセキュリティ] \> [回復] に移動します。 [Windows 7 に戻す] の下にある [開始する] を選択します。

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-11.png)

次に、Windows 10 から戻す理由について質問されます。 技術的な理由がある場合はそれを入力していただくと、問題の解決に向けた取り組みへのサポートとなり、お客様の経験を他のユーザーのために生かすことができます。

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-12.png)

多くの場合、使用する Windows 10 のバージョンに対して更新プログラムが発行されており、これにより技術的な問題が解決されている場合があります。 更新プログラムをチェックして見つかった場合はインストールし、発生した問題を解決できるかを確認することをお勧めします。

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-13.png)

更新プログラムを実行しても問題が解決せず、以前の Windows 7 のインストールに戻す必要がある場合は、Windows 10 を実行していた期間にインストールされたアプリなど、一部のアプリの再インストールが必要になる可能性があり、一部の設定も失われる場合があります。 重要な点ですが、Windows 10 を使用している期間中にローカルに保存したファイルやドキュメントはそのまま保持され、Windows 7 に戻した後もアクセスできます。 

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-14.png)

作業を開始する前に、以前の Windows 7 のインストールからのローカルまたはドメイン アカウントとパスワードが手元にあることを確認します。

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-15.png)

Windows 7 に戻すプロセスをこの画面から開始できます。 PC は数分後に Windows 7 で再起動され、Windows 10 にアップグレードする前と同じ環境に戻ります。

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-16.png)

## <a name="moving-to-windows-10-on-a-new-pc"></a>新しい PC での Windows 10 への移行

推奨される別の方法として、新しい PC で Windows 10 に移行する方法があります。 この方法を選択する場合は、古いコンピューターからファイルを移動させるのに、[OneDrive](https://support.office.com/article/b5e918be-0fd4-4095-98da-bceed57f8e0c?ocid=MoveToWindows10) のバックアップ、[Windows に組み込みのバックアップと復元機能](https://support.microsoft.com/help/4469209?ocid=MoveToWindows10)、[外部記憶装置](https://support.microsoft.com/ja-JP/help/4465814/windows-7-move-files-off-pc-with-an-external-storage-device?ocid=MoveToWindows10)を使用した手動による移動、または [Laplink の PCmover Express](https://www.microsoft.com/en-us/windows/transfer-your-data) などのツールを使用できます。 これらのいずれのオプションを使用した場合でも、Windows 10 に含まれていない必要なアプリケーションを再インストールする必要があります。 Windows 7 を実行している既存の PC から Windows 10 を実行する新しい PC に手動で移行するためのオプションの詳細については、「[Windows 10 PC への移行](https://support.microsoft.com/ja-JP/help/4229823?ocid=MoveToWindows10)」を参照してください。

## <a name="desktop-deployment-centerhttpsakamshowtoshift"></a>[デスクトップ展開センター](https://aka.ms/howtoshift)