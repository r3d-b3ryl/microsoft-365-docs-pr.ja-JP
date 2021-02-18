---
title: リファレンスポリシー、プラクティス、ガイドライン
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft はさまざまなポリシー、手順を開発し、さまざまな業界のベスト プラクティスを採用して、不正、望ましくない、または悪意のある電子メールからユーザーを保護しています。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1065fdef5f804214ca48f7ca54170e6e417490d7
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289211"
---
# <a name="reference-policies-practices-and-guidelines"></a>リファレンス: ポリシー、プラクティス、ガイドライン

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft は、Web 上におけるユーザー エクスペリエンスの信頼性を高めるための支援に取り組んでいます。 そのため、さまざまなポリシー、手順を作成し、業界のいくつものベスト プラクティスを採用して、ユーザーが不適切で望ましくない、または悪意のあるメールから保護されるよう取り組んできました。 ユーザーに電子メールを送信しようとする送信者は、この取り組みを支援し、潜在的な配信の問題を回避するために、完全に理解し、この記事のガイダンスに従っている必要があります。

これらのポリシーとガイドラインに準拠していない場合、Microsoft サポート チームの支援を受けられないことがあります。 この資料に記されているガイドライン、プラクティス、ポリシーを遵守しているものの、送信 IP アドレスに関して配信の問題が解決されない場合、以下の手順に従って除外要求を送信してください。 手順については、「リストから削除するポータルを使用して、受信拒否リストから自分自身を [削除する」を参照してください](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。

## <a name="general-microsoft-policies"></a>一般的な Microsoft ポリシー

Microsoft 365 ユーザーに送信される電子メールは、電子メールの送信と Microsoft 365 の使用に関する Microsoft ポリシーに準拠している必要があります。

- Microsoft 365 に適用されるサービスの使用条件特に、サービスを使用してスパムやマルウェアを配布したりしに対する禁止。

- [Microsoft サービス規約](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>政府の規制

Microsoft 365 ユーザーに送信される電子メールは、該当する管轄区域での電子メール通信に関する適用される法律および規制に従う必要があります。

- [CAN-SPAM 法:ビジネスのためのコンプライアンス ガイド](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [「削除してください」。応答と責任: 電子メールのマーケティング担当者は「登録解除」要求を受け入れる必要がある](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>テクニカル ガイドライン

Microsoft 365 に送信される電子メールは、以下のドキュメントに記載されている該当する推奨事項に準拠している必要があります (一部のリンクは英語でのみ利用可能です)。

- [RFC 2505:SMTP MTA のスパム対策の推奨事項](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920:コマンド パイプラインの SMTP サービス拡張機能](https://www.ietf.org/rfc/rfc2920.txt)

さらに、Microsoft 365 に接続する電子メール サーバーは、次の要件に従う必要があります。

- 送信者は、インターネット協会のインターネット技術標準化委員会 (IETF) が発行しているインターネット電子メールの送信に関する技術的な標準 (RFC 5321、RFC 5322 など) すべてに準拠していなければなりません。

- 500 から 599 までの数字の SMTP エラー メッセージ コード (別名、永続的な配信不能レポート (NDR)) を受け取る場合、送信者はそのメッセージを対象の受信者に再送信してはなりません。

- 何度か配信不能応答が出されたなら、送信者は対象の受信者に対して電子メールの送信を中止する必要があります。

- 安全でない電子メール中継サーバーまたはプロキシ サーバー経由でメッセージを転送しないでください。

- 登録解除する方法は、個別のリストからであれ、送信者がホストするすべてのリストからであれ、受信者が簡単に見つけて実行できるように明記されている必要があります。

- 動的 IP 領域からの接続は受け付けられません。

- 電子メール サーバーでは逆引き DNS レコードを有効にしておく必要があります。

## <a name="reputation-management"></a>評判の管理

送信者、ISP、およびその他のサービス プロバイダーは、積極的に、外部 IP アドレスの評価を管理する必要があります。

## <a name="microsoft-365-limits"></a>Microsoft 365 の制限

送信者は、Exchange Online Protection の制限に記載されている Microsoft 365 の制限 [に従う必要があります](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)。

## <a name="email-delivery-resources-and-organizations"></a>電子メール配信リソースと組織

Microsoft は、インターネットと電子メールのエコシステムを改善するために業界団体およびサービス プロバイダーと積極的に連携しています。これらの組織は、Microsoft がサポートし、送信者が準ずるよう推奨されているベスト プラクティスに関する資料を公開しています。これによって、世界の複数の電子メール サービス プロバイダー間で電子メールを配信することがより容易になります。

- [Messaging Malware Mobile Anti-Abuse Working Group](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.otalliance.org/resources)

- [Email Sender & Provider Coalition](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>迷惑行為とスパムの報告

不正、不正、望ましくない、または悪意のある電子メールを報告するには、「メッセージとファイルを Microsoft に報告する」を参照 [してください](report-junk-email-messages-to-microsoft.md)。 これらの種類の通信の送信は Microsoft ポリシーに違反し、確認済みレポートに対して適切なアクションが実行されます。

## <a name="law-enforcement"></a>法的処置

司法当局の一員で Office 365 に関する法的文書に関して Microsoft Corporation を支援してくださる方、または Microsoft に提出した法的文書に関して質問がある方は、(1) (425) 722-1299 までお電話ください。
