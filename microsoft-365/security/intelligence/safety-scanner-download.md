---
title: Microsoft セーフティ スキャナー ダウンロード
ms.reviewer: ''
description: Microsoft セーフティ スキャナー ツールを入手して、Windows コンピューターからマルウェアを見つけて削除します。
keywords: セキュリティ, マルウェア
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 2f0e3fd84a9df907aa50339a1e3a2108d023db81
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683527"
---
# <a name="microsoft-safety-scanner-download"></a>Microsoft セーフティ スキャナー ダウンロード

Microsoft セーフティ スキャナーは、Windows コンピューターからマルウェアを見つけて削除するように設計されたスキャン ツールです。 ダウンロードしてスキャンを実行するだけでマルウェアを見つけ、特定された脅威によって行われた変更を元に戻すことができます。

- **[Microsoft セーフティ スキャナーをダウンロードする (32 ビット)](https://go.microsoft.com/fwlink/?LinkId=212733)**

- **[Microsoft セーフティ スキャナーをダウンロードする (64 ビット)](https://go.microsoft.com/fwlink/?LinkId=212732)**

> [!NOTE]
> 2019 年 11 月以降、セーフティ スキャナー は SHA-2 のみで署名されます。 セキュリティ インテリジェンスを更新するには、SHA-2 をサポートするようにデバイスを更新する必要があります。 詳細については、「[Windows および WSUS の 2019 SHA-2 コード署名サポートの要件](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)」を参照してください。

## <a name="important-information"></a>インストールに関する重要な情報

- Microsoft セーフティ スキャナーのセキュリティ インテリジェンス更新プログラムのバージョンは、[この Web ページ](https://www.microsoft.com/wdsi/definitions)で説明されているバージョンと一致します。

- セーフティ スキャナーは、手動でトリガーされたときにのみスキャンされ、ダウンロード後 10 日間使用できます。 各スキャンの前に、このツールの最新バージョンを常にダウンロードすることをお勧めします。

- セーフティ スキャナーはポータブル実行可能ファイルであり、Windows スタート メニューやデスクトップ上のアイコンには表示されません。 このダウンロードを保存した場所に注意してください。

- このツールでは、マルウェア対策製品は置き換えられません。 自動更新によるリアルタイムの保護については、[Windows 11、Windows 10、および Windows 8 の場合は Microsoft Defender Antivirus を使用し](https://www.microsoft.com/windows/comprehensive-security)、[Windows 7 ではMicrosoft Security Essentials を使用してください](https://support.microsoft.com/help/14210/security-essentials-download)。 これらのマルウェア対策製品は、強力なマルウェア除去機能も提供します。 これらの製品でマルウェアの削除に問題がある場合は、 [困難な脅威の削除](https://www.microsoft.com/wdsi/help/troubleshooting-infection)に関するヘルプを参照してください。

## <a name="system-requirements"></a>システム要件

セーフティ スキャナー は、Windows 11、Windows 10、Windows 10 Tech Preview、Windows 8.1、Windows 8、Windows 7、Windows Server 2019、Windows Server 2016、Windows Server Tech Preview、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、または Windows Server 2008 を実行しているコンピューターから悪意のあるソフトウェアを削除するのに役立ちます 詳細については、 [Microsoft ライフサイクル ポリシー](/lifecycle/)を参照してください。

## <a name="how-to-run-a-scan"></a>スキャンを実行する方法

1. このツールをダウンロードして開きます。
2. 実行するスキャンの種類を選択し、スキャンを開始します。
3. 画面に表示されるスキャン結果を確認します。 詳細な検出結果については、 **%SYSTEMROOT%\debug\msert.log** でログを表示します。

このツールを削除するには、実行可能ファイルを削除します (既定では msert.exe です)。

セーフティ スキャナーの詳細については、[セーフティ スキャナー を 使用して問題をトラブルシューティングする方法](https://support.microsoft.com/kb/2520970)に関するサポート記事を参照してください。

## <a name="related-resources"></a>関連リソース

- [セーフティ スキャナーのトラブルシューティング](https://support.microsoft.com/help/2520970/how-to-troubleshoot-an-error-when-you-run-the-microsoft-safety-scanner)
- [Microsoft Defender ウイルス対策](https://www.microsoft.com/windows/comprehensive-security)
- [Microsoft Security Essentials](https://support.microsoft.com/help/14210/security-essentials-download)
- [困難な脅威の削除](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware)
- [マルウェア分析のためにファイルを送信する](https://www.microsoft.com/wdsi/filesubmission)
- [Microsoft マルウェア対策と脅威保護ソリューション](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)
