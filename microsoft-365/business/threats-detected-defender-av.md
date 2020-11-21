---
title: Microsoft Defender ウイルス対策によって検出された脅威
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Microsoft Defender ウイルス対策が、ウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威から Windows デバイスを保護する方法について説明します。
ms.openlocfilehash: e3c8a1071625bba41af5f3cccd50f8484acac18d
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376711"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策によって検出された脅威

Microsoft Defender ウイルス対策は、ウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威から Windows デバイスを保護します。

- 通常、ウイルスは、デバイスまたはネットワーク上の他のファイルにコードを添付することによって広がり、感染したプログラムが正しく動作しなくなる可能性があります。
- マルウェアには、悪意のあるファイル、アプリケーション、コードが含まれています。これにより、損傷が発生したり、デバイスの通常使用が中断されたりする また、マルウェアは、権限のないアクセスを許可したり、システムリソースを使用したり、パスワードやアカウント情報を盗んだり、コンピューターからロックしたり、ransom を求めたりすることができます。
- スパイウェアが web 参照アクティビティなどのデータを収集し、リモートサーバーにデータを送信します。
 
脅威保護を提供するために、Microsoft Defender ウイルス対策はいくつかの方法を使用します。 これらの方法には、クラウドで提供される保護、リアルタイム保護、および専用の保護更新が含まれます。

- クラウド提供の保護によって、ほぼ瞬時の脅威の検出とブロックが行われます。
- 常にスキャンは、ファイルとプロセス動作の監視と、その他の手法 ( *リアルタイム保護* とも呼ばれます) を使用します。
- 専任の保護の更新は、機械学習、人的および自動化された大規模なデータ分析、および徹底的な脅威抵抗調査に基づいています。 

マルウェアおよび Microsoft Defender ウイルス対策の詳細については、次の記事を参照してください。 

- [マルウェア & 他の脅威について](/windows/security/threat-protection/intelligence/understanding-malware)
- [Microsoft がマルウェアおよび望ましくない可能性のあるアプリケーションを特定する方法](/windows/security/threat-protection/intelligence/criteria)
- [Windows 10 での次世代の保護](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Microsoft 以外のウイルス対策ソリューションを使用した場合はどうなりますか? 

Microsoft Defender ウイルス対策は、オペレーティングシステムの一部であり、Windows 10 を実行しているデバイス上で有効になっています。 ただし、マイクロソフト以外のウイルス対策ソリューションを使用していて、 [エンドポイントに Microsoft defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)を使用していない場合、Microsoft Defender ウイルス対策は自動的に無効モードになります。  

無効モードになっている場合でも、ユーザーおよびお客様は Microsoft Defender ウイルス対策を使用して、スケジュールされた、またはオンデマンドのスキャンを行い、脅威を識別できます。ただし、Microsoft Defender ウイルス対策には、次のようになります。

- 既定のウイルス対策アプリとして使用されます。
- 脅威に対してファイルを積極的にスキャンします。
- 脅威を修復または解決します。

Microsoft 以外のウイルス対策ソリューションをアンインストールすると、Microsoft Defender ウイルス対策が自動的にアクティブモードになり、脅威から Windows デバイスが保護されます。

> [!TIP]
> - Microsoft 365 を使用している場合は、Microsoft Defender ウイルス対策をプライマリウイルス対策ソリューションとして使用することを検討してください。 統合は、より適切な保護を提供します。 詳細について [は、「Microsoft Defender ウイルス対策と Office 365」を](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)参照してください。
> - マイクロソフト以外のウイルス対策ソリューションを使用している場合でも、Microsoft Defender ウイルス対策を最新の状態に保つようにしてください。

## <a name="what-to-expect-when-threats-are-detected"></a>脅威が検出されたときに予想されること

Microsoft Defender ウイルス対策によって脅威が検出されると、次の処理が行われます。

- ユーザーが [Windows で通知を](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e)受信します。 
- 検出は、[**保護履歴**] ページの [ [Windows セキュリティアプリ](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)] に一覧表示されます。  
- [Windows 10 デバイスをセキュリティで保護](secure-win-10-pcs.md)して [Intune に登録](/mem/intune/enrollment/windows-enrollment-methods)した場合は、[**アクティブな脅威**] ページにある <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">microsoft 365 管理センター</a>での脅威の検出と洞察が表示されます。これは、**ホーム** ページの **microsoft Defender ウイルス対策** カード (または、「 **Health** threat & Antivirus」を選択することにより、ナビゲーションウィンドウからアクセスでき  >  **Threats & antivirus** ます)。
    > [!NOTE]
    > **Microsoft Defender ウイルス対策** カードおよび **アクティブな脅威** ページはフェーズでロールアウトされるため、すぐにアクセスできない場合があります。

ほとんどの場合、ユーザーは他の操作を行う必要はありません。 悪意のあるファイルまたはプログラムがデバイス上で検出されると、Microsoft Defender ウイルス対策によってブロックされ、実行が禁止されます。 さらに、新たに検出された脅威が、他のデバイスやユーザーも保護されるように、ウイルス対策およびマルウェア対策エンジンに追加されます。  

悪意のあるファイルの削除の承認など、ユーザーが実行する必要のあるアクションがある場合は、受信した通知にそのことが表示されます。 ユーザーに代わって、またはユーザーが実行する必要があるアクションの詳細については、「 [保護履歴](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708)」を参照してください。 IT プロフェッショナル/管理者として脅威検出を管理する方法については、「 [検出された脅威をレビューし、アクションを実行](review-threats-take-action.md)する」を参照してください。

さまざまな脅威の詳細については、 <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft セキュリティインテリジェンスの脅威のサイト</a>にアクセスして、次の操作を実行できます。 

- 主要な脅威に関する現在の情報を表示します。
- 特定の地域の最新の脅威を表示します。
- 特定の脅威の詳細については、「脅威の百科事典」を検索してください。

## <a name="related-content"></a>関連コンテンツ

[Windows 10 デバイスをセキュリティで保護](secure-windows-10-devices.md) する (記事) \
[Microsoft Defender ウイルス対策](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (記事) を評価する
[リアルタイムおよびクラウドで提供されるウイルス対策保護](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (記事) を有効にする方法 \
[Windows セキュリティアプリ (記事) から Microsoft Defender ウイルス対策をオンおよび使用する方法](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) \
[グループポリシーを使用して Microsoft Defender ウイルス対策を有効にする方法](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (記事) \
[ウイルス対策定義を更新する方法](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (記事) \
[マルウェアおよびマルウェア以外のを分析のために Microsoft に提出する方法](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (記事)