---
title: リファレンスポリシー、プラクティス、ガイドライン
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft は、さまざまなポリシー、手順を開発し、業界のベストプラクティスをいくつか採用して、ユーザーを不適切な迷惑メールや悪意のあるメールから保護しています。
ms.openlocfilehash: 9684453503329e955c21051885c5d93e8c927c48
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208212"
---
# <a name="reference-policies-practices-and-guidelines"></a>リファレンス: ポリシー、プラクティス、ガイドライン

Microsoft は、Web 上におけるユーザー エクスペリエンスの信頼性を高めるための支援に取り組んでいます。 そのため、さまざまなポリシー、手順を作成し、業界のいくつものベスト プラクティスを採用して、ユーザーが不適切で望ましくない、または悪意のあるメールから保護されるよう取り組んできました。 送信者は、ユーザーに電子メールを送信しようとしていることを確認し、この記事のガイダンスに従って、配信の問題が発生しないようにする必要があります。

これらのポリシーとガイドラインに準拠していない場合、Microsoft サポート チームの支援を受けられないことがあります。 この資料に記されているガイドライン、プラクティス、ポリシーを遵守しているものの、送信 IP アドレスに関して配信の問題が解決されない場合、以下の手順に従って除外要求を送信してください。 手順については、「[リストから除外のポータルを使用して、受信拒否リストから自分自身を削除する](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)」を参照してください。

## <a name="general-microsoft-policies"></a>一般的な Microsoft ポリシー

Microsoft 365 ユーザーに送信される電子メールは、電子メール転送および Microsoft 365 の使用を制御するすべての Microsoft ポリシーに準拠している必要があります。

- Microsoft 365 に適用されるサービスの条件具体的には、禁止は、サービスを使用してスパムまたはマルウェアを配布することについてのものではありません。

- [Microsoft サービス規約](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>政府の規制

Microsoft 365 ユーザーに電子メールを送信するには、該当する管轄区域で、電子メール通信を制御する該当するすべての法律および規制に従う必要があります。

- [CAN-SPAM 法:ビジネスのためのコンプライアンス ガイド](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [「削除してください」。応答と責任: 電子メールのマーケティング担当者は「登録解除」要求を受け入れる必要がある](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)

## <a name="technical-guidelines"></a>テクニカル ガイドライン

Microsoft 365 に送信される電子メールは、以下のドキュメントに記載されている該当する推奨事項に準拠する必要があります (一部のリンクは英語のみが利用できます)。

- [RFC 2505:SMTP MTA のスパム対策の推奨事項](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920:コマンド パイプラインの SMTP サービス拡張機能](https://www.ietf.org/rfc/rfc2920.txt)

また、Microsoft 365 に接続する電子メールサーバーは、次の要件を満たす必要があります。

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

送信者は、「 [Exchange Online Protection の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)」に記載されている Microsoft 365 の制限に従う必要があります。

## <a name="email-delivery-resources-and-organizations"></a>電子メール配信リソースと組織

Microsoft は、インターネットと電子メールのエコシステムを改善するために業界団体およびサービス プロバイダーと積極的に連携しています。これらの組織は、Microsoft がサポートし、送信者が準ずるよう推奨されているベスト プラクティスに関する資料を公開しています。これによって、世界の複数の電子メール サービス プロバイダー間で電子メールを配信することがより容易になります。

- [Messaging Malware Mobile Anti-Abuse Working Group](https://www.m3aawg.org/)

- [オンラインの信頼アライアンス](https://www.otalliance.org/resources)

- [電子メールの送信者 & プロバイダーの協力体制](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>迷惑行為とスパムの報告

不正な迷惑メール、迷惑メールを報告する方法については、「 [Microsoft へのレポートメッセージとファイル](report-junk-email-messages-to-microsoft.md)」を参照してください。 これらの種類の通信を送信することは、Microsoft ポリシーに違反するものであり、確認されたレポートに対して適切な処置が行われます。

## <a name="law-enforcement"></a>法的処置

司法当局の一員で Office 365 に関する法的文書に関して Microsoft Corporation を支援してくださる方、または Microsoft に提出した法的文書に関して質問がある方は、(1) (425) 722-1299 までお電話ください。
