---
title: ビジネス向け Microsoft Defender のファイアウォール
description: 構成設定をWindows Defender Microsoft Defender for Business のファイアウォールの詳細
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 1d85544d88004d3aa7654449eca4fb55db67e966
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61375456"
---
# <a name="firewall-in-microsoft-defender-for-business"></a>ビジネス向け Microsoft Defender のファイアウォール

> [!IMPORTANT]
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 この記事には、Microsoft Defender for Business (プレビュー) に含まれていない一部の機能について説明する可能性があるオンライン コンテンツへのリンクが含まれています。

Microsoft Defender for Business には、ファイアウォール機能とファイアウォールWindows Defender[があります](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。 ファイアウォール保護は、デバイスからの入力またはフローを許可されるネットワーク トラフィックを決定するルールを使用してデバイスをセキュリティで保護するのに役立ちます。 

ファイアウォール保護を使用して、さまざまな場所のデバイスでの接続を許可またはブロックするかどうかを指定できます。 たとえば、ファイアウォール設定では、会社の内部ネットワークに接続されているデバイスで受信接続を許可できますが、デバイスが信頼されていないデバイスを持つネットワーク上にある場合は、これらの接続を防止できます。

**この記事では、以下について説明します**。

- [Defender for Business の既定のファイアウォール設定](#default-firewall-settings-in-defender-for-business)
- [Defender for Business で構成できるファイアウォール設定](#firewall-settings-you-can-configure-in-defender-for-business)

## <a name="default-firewall-settings-in-defender-for-business"></a>Defender for Business の既定のファイアウォール設定

Microsoft Defender for Business には、会社のデバイスを 1 日目から保護するための既定のファイアウォール ポリシーと設定が含まれています。 会社のデバイスが Microsoft Defender for Business にオンボードされ次第、既定のファイアウォール ポリシーは次のように動作します。

- デバイスからの送信接続は、場所に関係なく、既定で許可されます。
- デバイスが会社のネットワークに接続されている場合、既定ではすべての受信接続が許可されます。
- デバイスがパブリック ネットワークまたはプライベート ネットワークに接続されている場合、既定ではすべての受信接続がブロックされます。

Microsoft Defender for Business では、着信接続をブロックまたは許可する例外を定義できます。 これらの例外は、カスタム ルールを作成して定義します。 「 [ファイアウォール ポリシーのカスタム ルールを管理する」を参照してください](mdb-custom-rules-firewall.md)。

## <a name="firewall-settings-you-can-configure-in-defender-for-business"></a>Defender for Business で構成できるファイアウォール設定

Microsoft Defender for Business には、ファイアウォールを介したファイアウォールWindows Defender含まれます。 次の表に、Microsoft Defender for Business でファイアウォール保護用に構成できる設定を示します。 <br/><br/>

| Setting | 説明 |
|--|--|
| **ドメイン ネットワーク** | ドメイン ネットワーク プロファイルは、会社のネットワークに適用されます。 ドメイン ネットワークのファイアウォール設定は、同じネットワーク上にある他のデバイスで開始される受信接続に適用されます。 既定では、受信接続は [すべて許可] **に設定されています**。  |
| **パブリック ネットワーク** | パブリック ネットワーク プロファイルは、喫茶店や空港などの公共の場所で使用できるネットワークに適用されます。 パブリック ネットワークのファイアウォール設定は、同じネットワーク上にある他のデバイスで開始される受信接続に適用されます。 パブリック ネットワークには、知らないデバイスや信頼できないデバイスを含め、受信接続は既定で [すべてブロック] **に** 設定されます。  |
| **プライベート ネットワーク** | プライベート ネットワーク プロファイルは、自宅などのプライベートな場所のネットワークに適用されます。 プライベート ネットワークのファイアウォール設定は、同じネットワーク上にある他のデバイスで開始される受信接続に適用されます。 一般に、プライベート ネットワークでは、同じネットワーク上の他のすべてのデバイスが信頼できるデバイスであると見なされます。 ただし、既定では、受信接続は [すべてブロック] **に設定されています**。 |
| **カスタム ルール** | [カスタム ルールを](mdb-custom-rules-firewall.md) 使用すると、特定の接続をブロックまたは許可できます。 たとえば、デバイス上の特定のアプリを介した接続を除き、プライベート ネットワークに接続されているデバイス上のすべての受信接続をブロックするとします。 この場合、プライベート ネットワークを **設定して** すべての受信接続をブロックし、例外を定義するカスタム ルールを追加します。 <br/><br/>カスタム ルールを使用して、特定のファイルまたはアプリ、インターネット プロトコル (IP) アドレス、または IP アドレスの範囲の例外を定義できます。 <br/><br/>作成するカスタム ルールの種類に応じて、使用できる値の例を次に示します。 <br/><br/>アプリケーション ファイルのパス: `C:\Windows\System\Notepad.exe or %WINDIR%\Notepad.exe` <br/><br/>IP: 有効な IPv4/IPv6 アドレス (例: `192.168.1.0``192.168.1.0/24` <br/><br/>IP: 有効な IPv4/IPv6 アドレス範囲 (スペースが含まれていない) のように書式設定 `192.168.1.0-192.168.1.9` されています。 |

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business でファイアウォール設定を管理する](mdb-custom-rules-firewall.md)

- [ファイアウォールの詳細Windows Defenderする](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)

- [Microsoft Defender for Business でのインシデントの表示と管理](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business での脅威への対応と軽減](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)