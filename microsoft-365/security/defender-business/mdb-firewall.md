---
title: Microsoft Defender for Businessのファイアウォール
description: 構成設定など、Microsoft Defender for BusinessのファイアウォールWindows Defenderについて説明します
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: fb506a1d2cc28329f9d6ef9975a10b0661379bb9
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664614"
---
# <a name="firewall-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessのファイアウォール

> [!IMPORTANT]
> Microsoft Defender for Businessは、2022 年 3 月 1 日以降、[Microsoft 365 Business Premium](../../business-premium/index.md)のお客様に展開されます。 スタンドアロン サブスクリプションとしての Defender for Business はプレビュー段階にあり、 [ここにサインアップ](https://aka.ms/mdb-preview) して要求する顧客と IT パートナーに段階的にロールアウトされます。 プレビューには [シナリオの初期セット](mdb-tutorials.md#try-these-preview-scenarios)が含まれており、定期的に機能を追加します。
> 
> この記事の一部の情報は、市販される前に大幅に変更される可能性があるプレリリースされた製品/サービスに関連しています。 Microsoft は、ここに記載されている情報に対して、明示的または黙示的な保証を行いません。 

Microsoft Defender for Businessには、[Windows Defender ファイアウォール](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)を使用したファイアウォール機能が含まれています。 ファイアウォール保護は、デバイスへの入り込みまたはデバイスからのフローが許可されているネットワーク トラフィックを決定するルールを使用してデバイスをセキュリティで保護するのに役立ちます。 

ファイアウォール保護を使用して、さまざまな場所のデバイスでの接続を許可するかブロックするかを指定できます。 たとえば、ファイアウォール設定では、会社の内部ネットワークに接続されているデバイスで受信接続を許可できますが、デバイスが信頼されていないデバイスを持つネットワーク上にある場合は、それらの接続を防ぐことができます。

**この記事では、次について説明します**。

- [Defender for Business の既定のファイアウォール設定](#default-firewall-settings-in-defender-for-business)

- [Defender for Business で構成できるファイアウォール設定](#firewall-settings-you-can-configure-in-defender-for-business)

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Businessに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="default-firewall-settings-in-defender-for-business"></a>Defender for Business の既定のファイアウォール設定

Microsoft Defender for Businessには、会社のデバイスを初日から保護するために役立つ既定のファイアウォール ポリシーと設定が含まれています。 会社のデバイスがMicrosoft Defender for Businessにオンボードされるとすぐに、既定のファイアウォール ポリシーは次のように機能します。

- デバイスからの送信接続は、場所に関係なく、既定で許可されます。
- デバイスが会社のネットワークに接続されている場合、既定ですべての受信接続がブロックされます。
- デバイスがパブリック ネットワークまたはプライベート ネットワークに接続されている場合、既定ですべての受信接続がブロックされます。

Microsoft Defender for Businessでは、受信接続をブロックまたは許可する例外を定義できます。 これらの例外は、カスタム ルールを作成して定義します。 [ファイアウォール ポリシーのカスタム ルールの管理に関するページを](mdb-custom-rules-firewall.md)参照してください。

## <a name="firewall-settings-you-can-configure-in-defender-for-business"></a>Defender for Business で構成できるファイアウォール設定

Microsoft Defender for Businessには、Windows Defender ファイアウォールによるファイアウォール保護が含まれます。 次の表に、Microsoft Defender for Businessのファイアウォール保護用に構成できる設定を示します。 <br/><br/>

| 設定 | 説明 |
|--|--|
| **ドメイン ネットワーク** | ドメイン ネットワーク プロファイルは、会社のネットワークに適用されます。 ドメイン ネットワークのファイアウォール設定は、同じネットワーク上にある他のデバイスで開始される受信接続に適用されます。 既定では、受信接続は **[すべてブロック]** に設定されます。  |
| **パブリック ネットワーク** | パブリック ネットワーク プロファイルは、コーヒー ショップや空港などのパブリックな場所で使用できるネットワークに適用されます。 パブリック ネットワークのファイアウォール設定は、同じネットワーク上にある他のデバイスで開始される受信接続に適用されます。 パブリック ネットワークには、知らないデバイスや信頼できないデバイスを含めることができるため、受信接続は既定で **[すべてブロック]** に設定されます。  |
| **プライベート ネットワーク** | プライベート ネットワーク プロファイルは、自宅などのプライベートな場所にあるネットワークに適用されます。 プライベート ネットワークのファイアウォール設定は、同じネットワーク上にある他のデバイスで開始される受信接続に適用されます。 一般に、プライベート ネットワークでは、同じネットワーク上の他のすべてのデバイスが信頼できるデバイスであると見なされます。 ただし、既定では、受信接続は **[すべてブロック]** に設定されます。 |
| **カスタム ルール** | [カスタム ルール](mdb-custom-rules-firewall.md) を使用すると、特定の接続をブロックまたは許可できます。 たとえば、デバイス上の特定のアプリ経由の接続を除き、プライベート ネットワークに接続されているデバイス上のすべての受信接続をブロックするとします。 この場合、 **プライベート ネットワーク** を設定してすべての受信接続をブロックし、例外を定義するカスタム規則を追加します。 <br/><br/>カスタム規則を使用して、特定のファイルまたはアプリ、インターネット プロトコル (IP) アドレス、または IP アドレスの範囲の例外を定義できます。 <br/><br/>作成するカスタム ルールの種類に応じて、使用できる値の例を次に示します。 <br/><br/>アプリケーション ファイルパス: `C:\Windows\System\Notepad.exe or %WINDIR%\Notepad.exe` <br/><br/>IP: 有効な IPv4/IPv6 アドレス (例:`192.168.11.0``192.168.1.0/24` <br/><br/>IP: 有効な IPv4/IPv6 アドレス範囲。次のように `192.168.1.0-192.168.1.9` 書式設定されます (スペースは含まれません)。 |

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Businessでファイアウォール設定を管理する](mdb-custom-rules-firewall.md)

- [ファイアウォールWindows Defender詳細を確認する](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)

- [Microsoft Defender for Businessでのインシデントの表示と管理](mdb-view-manage-incidents.md)

- [Microsoft Defender for Businessの脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)